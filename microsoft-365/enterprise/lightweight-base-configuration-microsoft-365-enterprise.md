---
title: 간단한 기본 구성
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 이 테스트 랩 가이드를 사용하여 Microsoft 365 Enterprise 테스트를 위한 간단한 테스트 환경을 만듭니다.
ms.openlocfilehash: 770ddf46f40036f0d711c7c30bdaebee7fdeef6e
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746534"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="09cdf-103">간단한 기본 구성</span><span class="sxs-lookup"><span data-stu-id="09cdf-103">The lightweight base configuration</span></span>

<span data-ttu-id="09cdf-104">이 문서에서는 Microsoft 365 E5 구독 및 Windows 10 Enterprise를 실행하는 컴퓨터에서 간소화된 환경을 만드는 방법에 대한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-104">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![간단한 Microsoft 365 Enterprise 테스트 환경](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="09cdf-106">결과로 나타난 환경을 사용하여 [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)의 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-106">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="09cdf-108">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-108">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="09cdf-109">1단계: Office 365 E5 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="09cdf-109">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="09cdf-110">[Office 365 개발/테스트 환경](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)의 2, 3단계의 세부 단계를 수행하여 경량의 Office 365 개발/테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-110">Follow the steps in Phase 2 and Phase 3 of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment) to create a lightweight Office 365 dev/test environment.</span></span>

>[!Note]
><span data-ttu-id="09cdf-111">우리는 사용자의 Office 365의 평가판 구독을 생성하여 개발/테스트 환경에 사용자가 현재 보유하고 있는 유료 구독과 별도의 Azure AD 테넌트를 보유하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-111">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="09cdf-112">이러한 분리는 프로덕션 구독에 영향을 주지 않고 테스트 테넌트의 사용자 및 그룹을 추가 및 제거할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-112">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
>
  
## <a name="phase-2-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="09cdf-113">2단계: Microsoft 365 E5 평가판 구독 추가.</span><span class="sxs-lookup"><span data-stu-id="09cdf-113">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="09cdf-114">이 단계에서는 Microsoft 365 E5 평가판 구독을 등록하고 Office 365 E5 평가판 구독과 동일한 조직에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-114">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="09cdf-115">우선, Microsoft 365 E5 평가판 구독을 추가하고 전역 관리자 계정에 Microsoft 365 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-115">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="09cdf-116">인터넷 브라우저의 개인 인스턴스를 사용하고 전역 관리자 계정 자격 증명으로 [https://admin.microsoft.com](https://admin.microsoft.com)의 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-116">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="09cdf-117">**Microsoft 365 관리 센터** 페이지에 있는 왼쪽 탐색 영역에서 **대금 청구 > 서비스 구매**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-117">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="09cdf-118">**서비스 구매** 페이지에서, **Microsoft 365 E5** 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-118">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="09cdf-119">마우스 포인터를 가져간 후 **평가판 시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-119">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="09cdf-120">**Microsoft 365 E5 평가판** 페이지에서 텍스트 또는 전화를 받도록 선택한 다음, 전화 번호를 입력하고, **문자 받기** 또는 **전화 받기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-120">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="09cdf-121">**주문 확인** 페이지에서 **지금 평가판 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-121">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="09cdf-122">**주문 접수** 페이지에서 **계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-122">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="09cdf-123">Microsoft 365 관리 센터에서 **활성 사용자**를 클릭 한 다음 관리자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-123">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="09cdf-124">**제품 라이센스**에 대한 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-124">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="09cdf-125">Office 365 Enterprise E5의 라이센스를 끄고 Microsoft 365 E5의 라이센스를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-125">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="09cdf-126">**저장 > 닫기 > 닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-126">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="09cdf-127">다음, [Office 365 개발/테스트 환경](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)의 ***3단계를 완료한 경우,*** 다른 모든 계정(사용자 2, 사용자 3, 사용자 4 및 사용자 5)에 대해 이전 절차의 8 및 11단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-127">Next, ***if you completed Phase 3 of the*** [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment), repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="09cdf-128">Microsoft 365 E5 평가판 구독은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-128">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="09cdf-129">영구 테스트 환경의 경우 소수의 라이선스를 사용해서 이 평가판 구독을 유료 구독으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-129">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="09cdf-130">이제 테스트 환경에는 다음이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-130">Your test environment now has:</span></span>
  
- <span data-ttu-id="09cdf-131">Microsoft 365 E5 평가판 구독.</span><span class="sxs-lookup"><span data-stu-id="09cdf-131">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="09cdf-132">모든 해당 사용자 계정(전역 관리자만 또는 5개의 사용자 계정 모두)이 Microsoft 365 E5를 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-132">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="09cdf-133">그림 1에서는 구성 결과, Microsoft 365 E5를 추가하는 계정, Office 365 및 EMS(Enterprise Security + Management)를 포함하는 계정을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-133">Figure 1 shows your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
<span data-ttu-id="09cdf-134">**그림 1: Microsoft 365 평가판 구독 추가**</span><span class="sxs-lookup"><span data-stu-id="09cdf-134">**Figure 1: Adding the Microsoft 365 trial subscription**</span></span>

![Microsoft 365 Enterprise 테스트 환경 2단계](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-3-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="09cdf-136">3단계: Windows 10 Enterprise 컴퓨터 만들기</span><span class="sxs-lookup"><span data-stu-id="09cdf-136">Phase 3: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="09cdf-137">이 단계에서는 Windows 10 Enterprise를 실행하는 독립 실행형 컴퓨터를 실제 컴퓨터, 가상 머신 또는 Azure Virtual Machine으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-137">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="09cdf-138">실제 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="09cdf-138">Physical computer</span></span>

<span data-ttu-id="09cdf-p104">개인용 컴퓨터를 구한 후 Windows 10 Enterprise를 설치합니다. Windows 10 Enterprise 평가판을 [여기](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p104">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="09cdf-141">가상 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="09cdf-141">Virtual machine</span></span>

<span data-ttu-id="09cdf-p105">사용자가 선택한 하이퍼바이저를 사용하여 가상 머신을 만들고 Windows 10 Enterprise를 설치합니다. Windows 10 Enterprise 평가판을 [여기](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p105">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="09cdf-144">Azure의 가상 머신</span><span class="sxs-lookup"><span data-stu-id="09cdf-144">Virtual machine in Azure</span></span>

<span data-ttu-id="09cdf-p106">Microsoft Azure에서 Windows 10 가상 머신을 만들려면 Windows 10 Enterprise에 대한 이미지에 액세스할 수 있는 ***Visual Studio 기반 구독이 있어야 합니다***. 다른 유형의 Azure 구독(예: 평가판 및 유료 구독)으로는 이 이미지에 액세스할 수 없습니다. 최신 정보를 보려면 [개발/테스트 시나리오에 Azure의 Windows 클라이언트 사용](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p106">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="09cdf-p107">다음 명령에서는 최신 버전의 Azure PowerShell을 사용합니다. [Azure PowerShell cmdlet 시작](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)을 참조하세요. 이러한 명령 집합은 WIN10이라는 Windows 10 Enterprise 가상 머신과 리소스 그룹, 저장소 계정 및 가상 네트워크를 포함하는 모든 필수 인프라를 빌드합니다. Azure 인프라 서비스에 이미 익숙한 경우 혅 배포된 인프라에 맞게 이러한 지침을 조정하세요.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p107">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="09cdf-152">먼저 Microsoft PowerShell 프롬프트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-152">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="09cdf-153">다음 명령을 사용하여 Azure 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-153">Sign in to your Azure account with the following command.</span></span>
  
```
Connect-AzAccount
```

<span data-ttu-id="09cdf-154">다음 명령을 사용하여 구독 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-154">Get your subscription name using the following command.</span></span>
  
```
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="09cdf-p108">Azure 구독을 설정합니다. \< 및 > 문자를 포함하여 따옴표 안에 있는 모든 것을 올바른 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p108">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="09cdf-p109">다음으로 새 리소스 그룹을 만듭니다. 고유한 리소스 그룹 이름을 확인하려면 이 명령을 사용하여 기존 리소스 그룹을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p109">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="09cdf-p110">이러한 명령을 사용하여 새 리소스 그룹을 만듭니다. \< 및 > 문자를 포함하여 따옴표 안에 있는 모든 내용을 올바른 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p110">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="09cdf-p111">그런 후 다음 명령을 사용하여 새 가상 네트워크와 WIN10 가상 머신을 만듭니다. 메시지가 표시되면 WIN10의 로컬 관리자 계정에 대한 이름 및 암호를 제공하고 이러한 항목을 안전한 장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p111">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-4-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="09cdf-163">4단계: Azure AD에 Windows 10 컴퓨터 가입</span><span class="sxs-lookup"><span data-stu-id="09cdf-163">Phase 4: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="09cdf-164">Windows 10 Enterprise가 있는 실제 또는 가상 머신을 만든 후에 로컬 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-164">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09cdf-165">Azure에 있는 가상 머신에는 [다음 지침](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)에 따라 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-165">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="09cdf-166">다음으로, WIN10 컴퓨터를 Microsoft 365 E5 구독의 Azure AD 테넌트에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-166">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="09cdf-167">WIN10 컴퓨터의 데스크톱에서 **시작 > 설정 > 계정 > 회사 또는 학교 액세스 > 연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-167">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="09cdf-168">**회사 또는 학교 계정 설정** 대화 상자에서 **Azure Active Directory에 이 장치 가입**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-168">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="09cdf-169">**회사 또는 학교 계정**에서 Microsoft 365 E5 구독의 전역 관리자 계정 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-169">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="09cdf-170">**암호 입력**에 전역 관리자 계정의 암호를 입력하고 **로그인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-170">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="09cdf-171">사용자의 조직이 맞는지 묻는 메시지가 표시되면 **가입**을 클릭하고 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-171">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="09cdf-172">설정 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-172">Close the settings window.</span></span>
    
<span data-ttu-id="09cdf-173">다음으로, WIN10 컴퓨터에 Office 365 ProPlus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-173">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="09cdf-174">Microsoft Edge 브라우저를 열고 글로벌 관리자 계정 자격 증명으로 Office 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-174">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="09cdf-175">도움을 받으려면 [Office 365에 로그인하는 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09cdf-175">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="09cdf-176">**Microsoft Office 홈** 탭에서 **Office 설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-176">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="09cdf-177">수행할 작업을 묻는 메시지가 표시되면 **실행**을 클릭하고 **사용자 계정 컨트롤**에 대해 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-177">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="09cdf-p113">Office 설치가 완료될 때까지 기다립니다. **모두 완료되었습니다.** 가 표시되면 **닫기**를 두 번 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-p113">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="09cdf-180">그림 3에서는 다음에 해당하는 WIN10 컴퓨터를 포함하는 결과 환경을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-180">Figure 3 shows your resulting environment, which includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="09cdf-181">Microsoft 365 E5 구독의 Azure AD 테넌트에 가입했습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-181">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="09cdf-182">Microsoft Intune(EMS)에서 Azure AD 장치로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-182">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="09cdf-183">Office 365 ProPlus가 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-183">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="09cdf-184">**그림 2: Microsoft 365 테스트 환경의 최종 구성**</span><span class="sxs-lookup"><span data-stu-id="09cdf-184">**Figure 2: The final configuration of the Microsoft 365 test environment**</span></span>

![Microsoft 365 Enterprise 테스트 환경 4단계](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="09cdf-186">이제 [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)의 추가 기능을 사용해볼 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-186">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="09cdf-187">다음 단계</span><span class="sxs-lookup"><span data-stu-id="09cdf-187">Next steps</span></span>

<span data-ttu-id="09cdf-188">다음과 같은 추가 테스트 랩 가이드 집합에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09cdf-188">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="09cdf-189">ID</span><span class="sxs-lookup"><span data-stu-id="09cdf-189">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="09cdf-190">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="09cdf-190">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="09cdf-191">정보 보호</span><span class="sxs-lookup"><span data-stu-id="09cdf-191">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="09cdf-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09cdf-192">See also</span></span>

[<span data-ttu-id="09cdf-193">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="09cdf-193">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="09cdf-194">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="09cdf-194">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="09cdf-195">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="09cdf-195">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
