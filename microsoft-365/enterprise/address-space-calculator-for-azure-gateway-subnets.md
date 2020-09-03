---
title: Azure 게이트웨이 서브넷에 대 한 주소 공간 계산기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/01/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
description: '요약: C3, Python 또는 PowerShell을 사용 하 여 Azure 게이트웨이 서브넷의 주소 공간을 계산 합니다.'
ms.openlocfilehash: 5e119f1ddefb5877886042b835ffdd093a34f0f8
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332796"
---
# <a name="address-space-calculator-for-azure-gateway-subnets"></a><span data-ttu-id="282be-103">Azure 게이트웨이 서브넷에 대 한 주소 공간 계산기</span><span class="sxs-lookup"><span data-stu-id="282be-103">Address space calculator for Azure gateway subnets</span></span>

<span data-ttu-id="282be-104">다른 네트워크에 연결 된 Azure 인프라 서비스의 VNet (가상 네트워크)에는 게이트웨이 서브넷이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="282be-104">A virtual network (VNet) in Azure infrastructure services that is connected to other networks must have a gateway subnet.</span></span> <span data-ttu-id="282be-105">이 서브넷을 정의 하는 최상의 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="282be-105">The best practices for defining this subnet are the following:</span></span>

- <span data-ttu-id="282be-106">게이트웨이 서브넷의 접두사 길이는 최대 접두사 길이는 29 개 (예: 10.119.255.248/29) 이지만, 현재 권장 사항은 접두사 길이 27 (예: 10.119.255.224/27)을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="282be-106">The prefix length of the gateway subnet can have a maximum prefix length of 29 (for example, 10.119.255.248/29), but the current recommendation is that you use a prefix length of 27 (for example, 10.119.255.224/27).</span></span>
- <span data-ttu-id="282be-107">게이트웨이 서브넷의 주소 공간을 정의할 때, VNet 주소 공간의 가장 최근 부분을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="282be-107">When defining the address space of the gateway subnet, use the very last part of the VNet address space.</span></span>

<span data-ttu-id="282be-108">두 번째 권장 사항을 위해 게이트웨이 서브넷에 사용 되는 비트를 0으로 설정 하 고 VNet 주소 공간에서 남은 변수 비트를 1로 지정 하 여 게이트웨이 서브넷의 주소 공간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="282be-108">For the second recommendation, you can determine the address space of the gateway subnet by setting the bits used for the gateway subnet to 0 and the remaining variable bits in the VNet address space to 1.</span></span> <span data-ttu-id="282be-109">Binary로 변환 하 고 10 진수로 변환할 필요 없이 게이트웨이 서브넷 주소 공간을 빠르게 계산 하려면 c # 이나 Python으로 작성 된 콘솔 응용 프로그램 또는 PowerShell 명령 블록을 사용 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="282be-109">To quickly calculate the gateway subnet address space without having to convert to binary and back to decimal, you can use a console application written in C# or Python or with a PowerShell command block.</span></span>

<span data-ttu-id="282be-110">이 문서에는 VNet 주소 접두사 및 게이트웨이 서브넷 접두사 길이의 w.x.y.z/n 값을 나타내는 c #, Python 및 PowerShell 코드 블록이 포함 되어 있으며, 게이트웨이 서브넷 주소 공간을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="282be-110">This article contains C#, Python and PowerShell code blocks that collect five integers—the values of w.x.y.z/n for the VNet address prefix and the gateway subnet prefix length—and calculates the gateway subnet address space.</span></span>

## <a name="c-code-block"></a><span data-ttu-id="282be-111">C # 코드 블록</span><span class="sxs-lookup"><span data-stu-id="282be-111">C# code block</span></span>

<span data-ttu-id="282be-112">이 코드 블록을 사용 하 여 c #에서 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="282be-112">Use this code block to create a console app in C#.</span></span>

```c#
using System; 
using System.Collections.Generic; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 
 
namespace ConsoleApplication1 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // Declare variables. 
            const long wOctet = 16777216;  
            const long xOctet = 65536; 
            const long yOctet = 256; 
            double D; 
            int w, x, y, z, vnetPrefLen, gwPrefLen; 
            long d, w2, x2, y2, z2; 
             
 
            // Get the five values needed from the keyboard. 
            Console.WriteLine("**************************************************************************"); 
            Console.WriteLine("*** Gateway subnet address space calculator for Azure virtual networks ***");             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine(); 
            Console.WriteLine("Please supply your virtual network address space in the form of w.x.y.z/n."); 
            Console.WriteLine(); 
            Console.WriteLine("w="); 
            w = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("x="); 
            x = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("y="); 
            y = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("z="); 
            z = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("n="); 
            vnetPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
            Console.WriteLine("Now supply the prefix length of your gateway subnet:"); 
            gwPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
 
            // Perform the calculation. 
            D = w * wOctet + x * xOctet + y * yOctet + z; 
            for (int i = vnetPrefLen + 1; i < gwPrefLen + 1; i++) 
            { 
                D = D + Math.Pow(2, 32 - i); 
            } 
            d = Convert.ToInt64(D); 
            w2 = d / wOctet; 
            x2 = (d - w2 * wOctet) / xOctet;  
            y2 = (d - w2 * wOctet - x2 * xOctet) / yOctet; 
            z2 = d - w2 * wOctet - x2 * xOctet - y2 * yOctet; 
             
            // Display the result.             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine("For the Azure virtual address space {0}.{1}.{2}.{3}/{4}", w, x, y, z, vnetPrefLen); 
            Console.WriteLine("and gateway prefix length of {0}, the gateway subnet address space is:", gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("{0}.{1}.{2}.{3}/{4}", w2, x2, y2, z2, gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("Press ENTER to quit."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="python-code-block"></a><span data-ttu-id="282be-113">Python 코드 블록</span><span class="sxs-lookup"><span data-stu-id="282be-113">Python code block</span></span>

<span data-ttu-id="282be-114">이 코드 블록을 사용 하 여 Python에서 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="282be-114">Use this code block to create a console app in Python.</span></span>

```python
import math 
# Collect the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet 
print("**************************************************************************")  
print("*** Gateway subnet address space calculator for Azure virtual networks ***")  
print("**************************************************************************\n")   
print("Please supply your virtual network address space in the form of w.x.y.z/n.");  
w=int(input("w = ")) 
x=int(input("x = ")) 
y=int(input("y = ")) 
z=int(input("z = ")) 
n=int(input("n = ")) 
print("")  
g=int(input("Now supply the prefix length of your gateway subnet: ")) 
print("")  
 
# Calculate  
wOctet = 16777216  
xOctet = 65536  
yOctet = 256  
D = w * wOctet + x * xOctet + y * yOctet + z 
for index in range(n + 1,g + 1): 
    D += 2**(32 - index)  
 
w2 = math.floor(D / wOctet)  
x2 = math.floor((D - w2 * wOctet) / xOctet) 
y2 = math.floor((D - w2 * wOctet - x2 * xOctet) / yOctet) 
z2 = D - w2 * wOctet - x2 * xOctet - y2 * yOctet  
 
# Display the result  
gwAddrPref= "Your gateway address prefix is: " + str(w2) + "." + str(x2) + "." + str(y2) + "." + str(z2) + "/" + str(g)  
print(gwAddrPref) 
```


## <a name="powershell-command-block"></a><span data-ttu-id="282be-115">PowerShell 명령 블록</span><span class="sxs-lookup"><span data-stu-id="282be-115">PowerShell command block</span></span>

<span data-ttu-id="282be-116">값을 입력 하 고 PowerShell 창 또는 PowerShell ISE에서 결과 명령 블록을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="282be-116">Fill in the values and run the resulting command block in a PowerShell window or in the PowerShell ISE.</span></span>

```powershell
# Specify the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet: 
$w= 
$x= 
$y= 
$z= 
$n= 
$g= 
# Calculate 
$wOctet = 16777216 
$xOctet = 65536 
$yOctet = 256 
[long]$D = $w * $wOctet + $x * $xOctet + $y * $yOctet + $z; 
for ($i = $n + 1; $i -lt $g + 1; $i++) 
{ 
$D = $D + [math]::pow(2, 32 - $i) 
} 
$w2 = [math]::floor($D / $wOctet) 
$x2 = [math]::floor( ($D - $w2 * $wOctet) / $xOctet ) 
$y2 = [math]::floor( ($D - $w2 * $wOctet - $x2 * $xOctet) / $yOctet ) 
$z2 = $D - $w2 * $wOctet - $x2 * $xOctet - $y2 * $yOctet 
# Display the result 
$dx= [string]$w2 + "." + [string]$x2 + "." + [string]$y2 + "." + [string]$z2 + "/" + [string]$g 
Write-Host "Your gateway address prefix is: " $dx
```
    
## <a name="related-topics"></a><span data-ttu-id="282be-117">관련 항목</span><span class="sxs-lookup"><span data-stu-id="282be-117">Related topics</span></span>

[<span data-ttu-id="282be-118">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="282be-118">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

