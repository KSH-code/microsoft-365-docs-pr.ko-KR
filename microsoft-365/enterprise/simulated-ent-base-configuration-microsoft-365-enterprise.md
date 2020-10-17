---
title: Microsoft 365의 시뮬레이이트된 엔터프라이즈 기반 구성
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 이 테스트 랩 가이드를 사용 하 여 엔터프라이즈에 대 한 Microsoft 365에 대 한 시뮬레이트된 엔터프라이즈 테스트 환경을 만듭니다.
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487663"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="79ff1-103">시뮬레이트된 엔터프라이즈 기본 구성</span><span class="sxs-lookup"><span data-stu-id="79ff1-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="79ff1-104">*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="79ff1-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="79ff1-105">이 문서에서는 다음을 포함 하는 엔터프라이즈 용 Microsoft 365의 단순화 된 환경을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-105">This article describes how to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="79ff1-106">Microsoft 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="79ff1-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="79ff1-107">인터넷에 연결 된 간소화 된 조직 인트라넷으로, Azure virtual network (DC1, APP1 및 CLIENT1)의 세 가지 가상 컴퓨터로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-107">A simplified organization intranet connected to the internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![시뮬레이트된 엔터프라이즈 기본 구성](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="79ff1-109">간단한 테스트 환경을 만들려면 다음 두 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-109">Creating a simplified test environment involves two phases:</span></span>
- [<span data-ttu-id="79ff1-110">1단계: 시뮬레이트된 인트라넷 만들기</span><span class="sxs-lookup"><span data-stu-id="79ff1-110">Phase 1: Create a simulated intranet</span></span>](#phase-1-create-a-simulated-intranet)
- [<span data-ttu-id="79ff1-111">2단계: Microsoft 365 E5 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="79ff1-111">Phase 2: Create your Microsoft 365 E5 subscription</span></span>](#phase-2-create-your-microsoft-365-e5-subscription)

<span data-ttu-id="79ff1-112">결과 환경을 사용 하 여 추가 [테스트 랩 가이드](m365-enterprise-test-lab-guides.md) 또는 자체를 사용 하 여 [기업에 대 한 Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise) 의 기능과 기능을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-112">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="79ff1-114">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="79ff1-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="79ff1-115">1단계: 시뮬레이트된 인트라넷 만들기</span><span class="sxs-lookup"><span data-stu-id="79ff1-115">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="79ff1-116">이 단계에서는 AD DS (Active Directory 도메인 서비스) 도메인 컨트롤러, 응용 프로그램 서버 및 클라이언트 컴퓨터를 포함 하는 Azure 인프라 서비스에 시뮬레이트된 인트라넷을 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-116">In this phase, build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span>

<span data-ttu-id="79ff1-117">이러한 컴퓨터를 추가 [Microsoft 365에서 엔터프라이즈 테스트 랩 가이드](m365-enterprise-test-lab-guides.md) 에 사용 하 여 하이브리드 id 및 기타 기능을 구성 하 고 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-117">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="79ff1-118">방법 1: Azure Resource Manager 템플릿으로 시뮬레이트된 인트라넷 만들기</span><span class="sxs-lookup"><span data-stu-id="79ff1-118">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="79ff1-119">이 방법에서는 Azure Resource Manager 템플릿을 사용 하 여 시뮬레이트된 인트라넷을 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-119">In this method, you use an Azure Resource Manager template to build out the simulated intranet.</span></span> <span data-ttu-id="79ff1-120">Azure Resource Manager 템플릿에는 Azure 네트워킹 인프라, 가상 컴퓨터 및 해당 구성을 만드는 모든 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-120">Azure Resource Manager templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="79ff1-121">서식 파일을 배포 하기 전에 [템플릿 추가 정보 페이지](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) 를 읽고 다음 정보를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-121">Before deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="79ff1-122">테스트 환경의 공용 DNS 도메인 이름 (testlab \<*your public domain*> )</span><span class="sxs-lookup"><span data-stu-id="79ff1-122">The public DNS domain name of your test environment (testlab.\<*your public domain*>).</span></span> <span data-ttu-id="79ff1-123">**사용자 지정 배포** 페이지의 **Domain Name (도메인 이름** ) 필드에이 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-123">You'll enter this name in the **Domain Name** field of the **Custom deployment** page.</span></span>
- <span data-ttu-id="79ff1-p103">가상 머신의 공용 IP 주소 URL에 대한 DNS 레이블 접두사입니다. **사용자 지정 배포** 페이지의 **DNS 레이블 접두사** 필드에 이 레이블을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="79ff1-126">지침을 읽은 후 [템플릿 추가 정보 페이지](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) 에서 **Azure에 배포** 를 선택 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-126">After you read through the instructions, select **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="79ff1-127">Azure Resource Manager 템플릿을 통해 작성 된 시뮬레이트된 인트라넷에는 유료 Azure 구독이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-127">The simulated intranet built by the Azure Resource Manager template requires a paid Azure subscription.</span></span>

<span data-ttu-id="79ff1-128">템플릿이 완료 된 후 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-128">After the template is complete, your configuration looks like this:</span></span>

![Azure 인프라 서비스의 시뮬레이트된 인트라넷](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="79ff1-130">방법 2: Azure PowerShell로 시뮬레이트된 인트라넷 만들기</span><span class="sxs-lookup"><span data-stu-id="79ff1-130">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="79ff1-131">이 방법에서는 Windows PowerShell 및 Azure PowerShell 모듈을 사용하여 네트워킹 인프라, 가상 머신 및 해당 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-131">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="79ff1-p104">PowerShell을 통해 한 번에 하나의 단계씩 Azure 인프라의 요소를 만들려는 경우 이 방법을 사용합니다. Azure에서 다른 가상 머신을 직접 배포하기 위해 PowerShell 명령 블록을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="79ff1-134">1단계: DC1 만들기</span><span class="sxs-lookup"><span data-stu-id="79ff1-134">Step 1: Create DC1</span></span>

<span data-ttu-id="79ff1-135">이 단계에서는 Azure virtual network를 만들고 AD DS 도메인에 대 한 도메인 컨트롤러인 가상 컴퓨터를 DC1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-135">In this step, you create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="79ff1-136">먼저, 로컬 컴퓨터에서 Windows PowerShell 명령 프롬프트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-136">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79ff1-p105">다음 명령 집합은 최신 버전의 Azure PowerShell을 사용합니다. [Azure PowerShell cmdlet으로 시작](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="79ff1-139">다음 명령을 사용하여 Azure 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-139">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="79ff1-140">다음 명령을 사용하여 구독 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-140">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="79ff1-141">Azure 구독을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-141">Set your Azure subscription.</span></span> <span data-ttu-id="79ff1-142">꺾쇠 괄호 ("<" 및 ">")를 포함 하 여 따옴표 안에 있는 모든 것을 올바른 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-142">Replace everything within the quotation marks, including the angle brackets ("<" and ">"), with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="79ff1-p107">다음으로 시뮬레이트된 엔터프라이즈 테스트 랩에 대한 새 리소스 그룹을 만듭니다. 고유한 리소스 그룹 이름을 확인하려면 이 명령을 사용하여 기존 리소스 그룹을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="79ff1-145">이러한 명령을 사용하여 새 리소스 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-145">Create your new resource group with these commands.</span></span> <span data-ttu-id="79ff1-146">꺾쇠 괄호를 포함 하 여 따옴표 안에 있는 모든 것을 올바른 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-146">Replace everything within the quotation marks, including the angle brackets, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="79ff1-147">그런 다음 시뮬레이트된 엔터프라이즈 환경의 회사 네트워크 서브넷을 호스팅하고 네트워크 보안 그룹을 사용 하 여 보호 하는 TestLab 가상 네트워크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-147">Next, create the TestLab virtual network that will host the corporate network subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="79ff1-148">리소스 그룹의 이름을 입력 하 고 로컬 컴퓨터의 PowerShell 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-148">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="79ff1-149">다음으로, DC1 가상 머신을 만들고 **testlab.**\<your public domain> AD DS 도메인에 대한 도메인 컨트롤러와</span><span class="sxs-lookup"><span data-stu-id="79ff1-149">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="79ff1-150">TestLab 가상 네트워크의 가상 머신에 대한 DNS 서버로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-150">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="79ff1-151">예를 들어 공용 도메인 이름이 **<span>contoso</span>.com**이면 DC1 가상 머신은 **<span>testlab</span>.contoso.com**에 대한 도메인 컨트롤러가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-151">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="79ff1-152">DC1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-152">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="79ff1-p111">DC1의 로컬 관리자 계정에 대한 사용자 이름과 암호를 입력하라는 메시지가 표시됩니다. 강력한 암호를 사용하고 이름 및 암호를 안전한 위치에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="79ff1-155">다음으로, DC1 가상 컴퓨터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-155">Next, connect to the DC1 virtual machine:</span></span>
  
1. <span data-ttu-id="79ff1-156">[Azure portal](https://portal.azure.com)에서 **리소스 그룹** > <***새 리소스 그룹의 이름***> > **DC1**  >  **연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-156">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <***the name of your new resource group***> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="79ff1-157">열기 창에서 **RDP 파일 다운로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-157">In the open pane, select **Download RDP file**.</span></span> <span data-ttu-id="79ff1-158">다운로드 된 DC1 파일을 열고 **연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-158">Open the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="79ff1-159">DC1 로컬 관리자 계정 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-159">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="79ff1-160">Windows 7:</span><span class="sxs-lookup"><span data-stu-id="79ff1-160">For Windows 7:</span></span>
    
     <span data-ttu-id="79ff1-161">**Windows 보안** 대화 상자에서 **다른 계정 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-161">In the **Windows Security** dialog box, select **Use another account**.</span></span> <span data-ttu-id="79ff1-162">**사용자 이름**에 \*\*DC1 \\ \*\* < *로컬 관리자 계정 이름*>를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-162">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
   - <span data-ttu-id="79ff1-163">Windows 8.1 또는 Windows 10:</span><span class="sxs-lookup"><span data-stu-id="79ff1-163">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="79ff1-164">**Windows 보안** 대화 상자에서 **기타 항목**을 선택 하 고 **다른 계정 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-164">In the **Windows Security** dialog box, select **More choices**, and then select **Use a different account**.</span></span> <span data-ttu-id="79ff1-165">**사용자 이름**에 \*\*DC1 \\ \*\* < *로컬 관리자 계정 이름*>를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-165">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="79ff1-166">**암호**에서 로컬 관리자 계정의 암호를 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-166">In **Password**, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="79ff1-167">메시지가 표시 되 면 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-167">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="79ff1-168">다음으로 DC1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 사용하여 추가 데이터 디스크를 드라이브 문자 F:의 새로운 볼륨으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-168">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="79ff1-169">그런 다음, DC1을 **testlab.**\<*your public domain*> 도메인에 대한 도메인 컨트롤러 및 DNS 서버로</span><span class="sxs-lookup"><span data-stu-id="79ff1-169">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<*your public domain*></span></span> <span data-ttu-id="79ff1-170">구성합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-170">domain.</span></span> <span data-ttu-id="79ff1-171">공용 도메인 이름을 지정 하 고 꺾쇠 괄호를 제거한 다음 DC1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-171">Specify your public domain name, remove the angle brackets, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="79ff1-p116">안전 모드 관리자 암호를 지정해야 합니다. 이 암호를 안전한 장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="79ff1-174">이러한 명령은 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-174">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="79ff1-175">DC1이 다시 시작되면 DC1 가상 머신에 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-175">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="79ff1-176">[Azure portal](https://portal.azure.com)에서 리소스 *그룹 이름이* **DC1**연결> >  > <**리소스 그룹** 을 선택  >  **Connect**합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-176">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <*your resource group name*> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="79ff1-177">다운로드 된 DC1 파일을 실행 한 다음 **연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-177">Run the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="79ff1-178">**Windows 보안**에서 **다른 계정 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-178">In **Windows Security**, select **Use another account**.</span></span> <span data-ttu-id="79ff1-179">**사용자 이름**에 \*\*testlab \\ \*\* < *로컬 관리자 계정 이름*>를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-179">In **User name**, enter **TESTLAB\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="79ff1-180">**암호** 상자에 로컬 관리자 계정의 암호를 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-180">In the **Password** box, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="79ff1-181">메시지가 표시 되 면 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-181">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="79ff1-182">다음으로, TESTLAB 도메인 구성원 컴퓨터에 로그인 할 때 사용 될 사용자 계정을 Active Directory에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-182">Next, create a user account in Active Directory that will be used when signing in to TESTLAB domain member computers.</span></span> <span data-ttu-id="79ff1-183">관리자 수준의 Windows PowerShell 명령 프롬프트에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-183">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="79ff1-184">이 명령은 User1 계정 암호를 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-184">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="79ff1-185">이 계정은 모든 TESTLAB 도메인 구성원 컴퓨터에 대 한 원격 데스크톱 연결에 사용 되므로 강력한 암호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-185">This account will be used for remote desktop connections for all TESTLAB domain member computers, so choose a strong password.</span></span> <span data-ttu-id="79ff1-186">User1 계정 암호를 기록 하 고 보안 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-186">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="79ff1-p120">다음으로, 새 User1 계정을 도메인, 엔터프라이즈 및 스키마 관리자로 구성합니다. 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="79ff1-189">DC1과의 원격 데스크톱 세션을 닫은 후 TESTLAB\\User1 계정을 사용하여 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-189">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="79ff1-190">다음으로, Ping 도구에 대한 트래픽을 허용하려면 관리자 수준의 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-190">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="79ff1-191">현재 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-191">Your current configuration looks like this:</span></span>
  
![시뮬레이트된 엔터프라이즈 기반 구성 1단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="79ff1-193">2단계: APP1 구성</span><span class="sxs-lookup"><span data-stu-id="79ff1-193">Step 2: Configure APP1</span></span>

<span data-ttu-id="79ff1-194">이 단계에서는 처음에 웹 및 파일 공유 서비스를 제공하는 응용 프로그램 서버인 APP1을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-194">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="79ff1-195">APP1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-195">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="79ff1-196">다음으로, APP1 로컬 관리자 계정 이름과 암호를 사용하여 APP1 가상 머신에 연결하고 Windows PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-196">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="79ff1-197">APP1와 DC1 사이의 이름 확인과 네트워크 통신을 확인하려면 **ping dc1.testlab.**\<*your public domain name*>을(를) 실행하고</span><span class="sxs-lookup"><span data-stu-id="79ff1-197">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="79ff1-198">응답이 4개인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-198">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="79ff1-199">다음으로, Windows PowerShell 프롬프트에 다음 명령을 사용하여 APP1 가상 머신을 TESTLAB 도메인에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-199">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="79ff1-200">**컴퓨터 추가** 명령을 실행 한 후에는 testlab \\ User1 도메인 계정 자격 증명을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-200">Note that you after you run the **Add-Computer** command, you must supply the TESTLAB\\User1 domain account credentials.</span></span>
  
<span data-ttu-id="79ff1-201">APP1을 다시 시작한 후에 TESTLAB\\User1 계정을 사용하여 연결한 후 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-201">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="79ff1-202">다음으로, APP1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 사용하여 APP1을 웹 서버로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-202">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="79ff1-203">그런 후 다음 PowerShell 명령을 사용하여 APP1의 폴더 내에 공유 폴더 및 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-203">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="79ff1-204">현재 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-204">Your current configuration looks like this:</span></span>
  
![시뮬레이트된 엔터프라이즈 기반 구성 2단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="79ff1-206">3단계: CLIENT1 구성</span><span class="sxs-lookup"><span data-stu-id="79ff1-206">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="79ff1-207">이 단계에서는 인트라넷에서 전형적인 랩톱, 태블릿 또는 데스크톱 컴퓨터의 역할을 하는 CLIENT1을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-207">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="79ff1-p122">다음 명령 집합은 Windows Server 2016 Datacenter를 실행하는 CLIENT1을 만듭니다. 이 작업은 모든 유형의 Azure 구독에서 수행할 수 있습니다. Visual Studio 기반 Azure 구독이 있는 경우 [Azure Portal](https://portal.azure.com)을 사용하여 Windows 10이 실행되는 CLIENT1을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span>
  
<span data-ttu-id="79ff1-210">CLIENT1에 대 한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력 하 고 로컬 컴퓨터의 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-210">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="79ff1-211">다음으로, CLIENT1 로컬 관리자 계정 이름과 암호를 사용하여 CLIENT1 가상 머신에 연결하고 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-211">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="79ff1-212">APP1와 DC1 사이의 이름 확인과 네트워크 통신을 확인하려면 Windows PowerShell 명령 프롬프트에서 **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="79ff1-212">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="79ff1-213">명령을 실행하고 응답이 4개인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-213">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="79ff1-214">다음으로, Windows PowerShell 프롬프트에 다음 명령을 사용하여 CLIENT1 가상 머신을 TESTLAB 도메인에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-214">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="79ff1-215">**Add-Computer** 명령을 실행한 후 TESTLAB\\User1 도메인 계정 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-215">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="79ff1-216">CLIENT1을 다시 시작한 후에 TESTLAB\\User1 계정 이름 및 암호를 사용하여 연결한 후 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-216">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="79ff1-217">그런 후 CLIENT1에서 APP1의 웹 및 파일 공유 리소스에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-217">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="79ff1-218">서버 관리자의 트리 창에서 **로컬 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-218">In Server Manager, in the tree pane, select **Local Server**.</span></span>
    
2. <span data-ttu-id="79ff1-219">**CLIENT1의 속성**에서 **IE 보안 강화 구성**옆에 **있는** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="79ff1-220">**Internet Explorer 보안 강화 구성**에서 **관리자** 및 **사용자**에 대해 **끄기를** 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-220">In **Internet Explorer Enhanced Security Configuration**, select **Off** for **Administrators** and **Users**, and then select **OK**.</span></span>
    
4. <span data-ttu-id="79ff1-221">시작 화면에서 **Internet Explorer**를 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-221">From the Start screen, select **Internet Explorer**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="79ff1-222">주소 표시줄에 **http<span>://</span>app1**를 입력 하 \<*your public domain name*> **/** 고 enter 키 **를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-222">In the address bar, enter **http<span>://</span>app1.testab.**\<*your public domain name*>**/**, and then press **Enter**.</span></span> <span data-ttu-id="79ff1-223">APP1에 대한 기본 인터넷 정보 서비스 웹 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-223">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="79ff1-224">바탕 화면 작업 표시줄에서 파일 탐색기 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-224">On the desktop taskbar, select the File Explorer icon.</span></span>
    
7. <span data-ttu-id="79ff1-225">주소 표시줄에 \*\* \\ \\ app1 \\ 파일\*\* **을 입력 한 다음 enter 키를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-225">In the address bar, enter **\\\\app1\\Files**, and then press **Enter**.</span></span> <span data-ttu-id="79ff1-226">파일 공유 폴더의 내용이 포함 된 폴더 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-226">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="79ff1-p126">**Files** 공유 폴더 창에서 **Example.txt** 파일을 두 번 클릭합니다. Example.txt 파일의 내용을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="79ff1-229">**example.txt - 메모장**과 **Files** 공유 폴더 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-229">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="79ff1-230">현재 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-230">Your current configuration looks like this:</span></span>
  
![시뮬레이트된 엔터프라이즈 기반 구성 3단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="79ff1-232">2단계: Microsoft 365 E5 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="79ff1-232">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="79ff1-p127">이 단계에서는 프로덕션 구독과는 별개인 새롭고 일반적인 Azure AD 테넌트를 사용하는 새 Microsoft 365 E5 구독을 만듭니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p127">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="79ff1-235">Microsoft 365 E5 평가판 구독을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-235">Use a trial subscription of Microsoft 365 E5.</span></span>

  <span data-ttu-id="79ff1-p128">Microsoft 365 E5 평가판 구독 기간은 30일로, 60일까지 쉽게 연장할 수 있습니다. 평가판 구독이 만료되면 유료 구독으로 전환하거나 새 평가판 구독을 만들어야 합니다. 새 평가판 구독을 만든다는 것은 복잡한 시나리오를 포함하는 구성을 벗어난다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-p128">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="79ff1-239">적은 수의 라이선스로 Microsoft 365 E5의 별도 프로덕션 구독을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-239">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="79ff1-240">이는 추가 비용 이지만 만료 되지 않은 작동 하는 테스트 환경이 있음을 보장 합니다. 이 경우에는 기능, 구성 및 시나리오를 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-240">This is an additional cost, but ensures that you have a working test environment that doesn't expire; in it, you can try features, configurations, and scenarios.</span></span> <span data-ttu-id="79ff1-241">개념 증명, 예제 및 응용 프로그램 개발 및 테스트에 대해 설명 하는 장기적으로 동일한 테스트 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-241">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="79ff1-242">이 방법이 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-242">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="79ff1-243">Office 365 E5 평가판 구독 등록</span><span class="sxs-lookup"><span data-stu-id="79ff1-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="79ff1-244">Azure portal에서 CORP\User1 계정을 사용 하 여 CLIENT1에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-244">From the Azure portal, connect to CLIENT1 with the CORP\User1 account.</span></span>

<span data-ttu-id="79ff1-245">새 Office 365 E5 평가판 구독을 만들려면 간단한 기본 구성 테스트 랩 가이드의 [1단계 ](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription)에 있는 지침을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="79ff1-245">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="79ff1-246">새 Office 365 E5 평가판 구독을 구성하려면 간단한 기본 구성 테스트 랩 가이드의 [2단계 ](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription)에 있는 지침을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="79ff1-246">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="79ff1-247">Office 365 E5 테스트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="79ff1-247">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="79ff1-248">Office 365 테스트 환경만 필요한 경우이 문서의 나머지 부분을 읽을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-248">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="79ff1-249">Microsoft 365 및 Office 365에 모두 적용 되는 추가 테스트 랩 가이드에 대 한 자세한 내용은 [microsoft 365 for Enterprise Test Lab 가이드](m365-enterprise-test-lab-guides.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="79ff1-249">For additional Test Lab Guides that apply to both Microsoft 365 and Office 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="79ff1-250">Microsoft 365 E5 평가판 구독 추가</span><span class="sxs-lookup"><span data-stu-id="79ff1-250">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="79ff1-251">Microsoft 365 E5 평가판 구독을 추가 하 고 라이선스를 사용 하 여 사용자 계정을 구성 하려면 경량 기본 구성 테스트 랩 가이드의 [3 단계](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) 에 나와 있는 지침을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-251">To add a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="79ff1-252">결과</span><span class="sxs-lookup"><span data-stu-id="79ff1-252">Results</span></span>

<span data-ttu-id="79ff1-253">이제 테스트 환경에는 다음이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-253">Your test environment now has:</span></span>
  
- <span data-ttu-id="79ff1-254">Microsoft 365 E5 평가판 구독.</span><span class="sxs-lookup"><span data-stu-id="79ff1-254">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="79ff1-255">모든 적절한 사용자 계정이 Microsoft 365 E5를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-255">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="79ff1-256">시뮬레이션되고 단순화된 인트라넷.</span><span class="sxs-lookup"><span data-stu-id="79ff1-256">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="79ff1-257">최종 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-257">Your final configuration looks like this:</span></span>
  
![시뮬레이트된 엔터프라이즈 기반 구성 2단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="79ff1-259">이제 [엔터프라이즈 용 Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise)의 추가 기능을 시험해 볼 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-259">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="79ff1-260">다음 단계</span><span class="sxs-lookup"><span data-stu-id="79ff1-260">Next steps</span></span>

<span data-ttu-id="79ff1-261">다음과 같은 추가 테스트 랩 가이드 집합에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="79ff1-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="79ff1-262">ID</span><span class="sxs-lookup"><span data-stu-id="79ff1-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="79ff1-263">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="79ff1-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="79ff1-264">정보 보호</span><span class="sxs-lookup"><span data-stu-id="79ff1-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="79ff1-265">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79ff1-265">See also</span></span>

[<span data-ttu-id="79ff1-266">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="79ff1-266">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="79ff1-267">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="79ff1-267">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="79ff1-268">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="79ff1-268">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
