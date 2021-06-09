---
title: Microsoft 365 테스트 환경에 대한 페더레이션 ID
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: '요약: Microsoft 365 테스트 환경에 대한 페더레이션 인증을 구성합니다.'
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487687"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0f1bc-103">Microsoft 365 테스트 환경에 대한 페더레이션 ID</span><span class="sxs-lookup"><span data-stu-id="0f1bc-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0f1bc-104">*이 테스트 랩 가이드는 엔터프라이즈 및 엔터프라이즈용 Microsoft 365 둘 다에 사용할 Office 365 Enterprise 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="0f1bc-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="0f1bc-p101">Microsoft 365는 페더레이션 ID를 지원합니다. 즉, 자격 증명 자체의 유효성 검사를 수행하는 대신, Microsoft 365는 Microsoft 365가 신뢰하는 페더레이션 인증 서버에 사용자를 연결하는 것을 의미합니다. 사용자의 자격 증명이 올바른 경우 페더레이션 인증 서버는 보안 토큰을 발급하며, 그런 후에 클라이언트는 인증의 증거로 해당 보안 토큰을 Microsoft 365로 전송합니다. 페더레이션 ID를 사용하면 Microsoft 365 구독과 고급 인증 및 보안 시나리오의 부하 부담을 줄이고 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="0f1bc-109">이 문서에서는 Microsoft 365 환경에 대해 페더티된 인증을 구성하여 다음과 같은 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![Microsoft 365 테스트 환경에 대한 페더레이션 인증](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="0f1bc-111">이 구성 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="0f1bc-112">평가 Microsoft 365 E5 또는 프로덕션 구독입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="0f1bc-113">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 5개의 가상 머신(DC1, APP1, CLIENT1, ADFS1 및 PROXY1)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="0f1bc-114">Azure AD 커넥트 ACTIVE Directory 도메인 서비스 도메인의 계정 목록을 동기화하기 위해 APP1에서 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="0f1bc-115">PROXY1은 들어오는 인증 요청을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="0f1bc-116">ADFS1은 DC1을 사용하여 자격 증명의 유효성을 검사하고 보안 토큰을 발행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="0f1bc-117">이 테스트 환경 설정에는 다음 다섯 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="0f1bc-118">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="0f1bc-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="0f1bc-119">2단계: AD FS 서버 만들기</span><span class="sxs-lookup"><span data-stu-id="0f1bc-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="0f1bc-120">3단계: 웹 프록시 서버 만들기</span><span class="sxs-lookup"><span data-stu-id="0f1bc-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="0f1bc-121">4단계: 자체 서명된 인증서를 만들고 ADFS1 및 PROXY1을 구성</span><span class="sxs-lookup"><span data-stu-id="0f1bc-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="0f1bc-122">5단계: 페더레이션 ID에 대해 Microsoft 365를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="0f1bc-123">Azure 평가판 구독으로는 이 테스트 환경을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0f1bc-124">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="0f1bc-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0f1bc-125">에 대한 암호 [해시 동기화의 지침을 Microsoft 365.](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="0f1bc-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="0f1bc-126">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-126">Your resulting configuration looks like this:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="0f1bc-128">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="0f1bc-129">평가 Microsoft 365 E5 또는 유료 구독입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="0f1bc-130">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="0f1bc-131">Azure AD 커넥트 APP1에서 실행되어 TESTLAB AD DS(Active Directory 도메인 서비스) 도메인을 주기적으로 Microsoft 365 구독의 Azure AD 테넌트와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="0f1bc-132">2단계: AD FS 서버 만들기</span><span class="sxs-lookup"><span data-stu-id="0f1bc-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="0f1bc-133">AD FS 서버는 Microsoft 365와 DC1에 호스트된 corp.contoso.com 도메인의 계정 간에 페더레이션 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="0f1bc-134">ADFS1에 대한 Azure Virtual Machine을 만들려면 구독 및 리소스 그룹의 이름, 기본 구성에 대한 Azure 위치를 입력한 후 로컬 컴퓨터의 Azure PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="0f1bc-135">다음으로, [Azure Portal](https://portal.azure.com)에서 ADFS1 로컬 관리자 계정 이름과 암호를 사용하여 ADFS1 가상 머신에 연결하고 Windows PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="0f1bc-136">ADFS1과 DC1 사이의 이름 확인 및 네트워크 통신을 확인하려면 **ping dc1.corp.contoso.com** 명령을 실행하고 4개의 응답이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="0f1bc-137">다음으로, ADFS1의 Windows PowerShell 프롬프트에 다음 명령을 사용하여 ADFS1 가상 머신을 CORP 도메인에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="0f1bc-138">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-138">Your resulting configuration looks like this:</span></span>
  
![AD FS 서버가 Microsoft 365 테스트 환경에 추가됨](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="0f1bc-140">3단계: 웹 프록시 서버 만들기</span><span class="sxs-lookup"><span data-stu-id="0f1bc-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="0f1bc-141">PROXY1은 인증을 시도하는 사용자와 ADFS1 간의 인증 메시지 프록시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="0f1bc-142">PROXY1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름과 Azure 위치를 입력하고, 로컬 컴퓨터의 Azure PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="0f1bc-143">PROXY1은 이 머신을 가리키는 공용 DNS 레코드를 만들게 되고, PROXY1 가상 머신을 다시 시작할 때 변경되지 않아야 하므로 고정 공용 IP 주소가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="0f1bc-144">다음으로, CorpNet 서브넷에 대한 네트워크 보안 그룹에 규칙을 추가하여 인터넷에서 PROXY1의 개인 IP 주소 및 TCP 포트 443으로의 원치 않는 인바운드 트래픽을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="0f1bc-145">로컬 컴퓨터의 Azure PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="0f1bc-146">다음으로, [Azure Portal](https://portal.azure.com)에서 PROXY1 로컬 관리자 계정 이름과 암호를 사용하여 PROXY1 가상 머신에 연결하고 PROXY1에서 Windows PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="0f1bc-147">RPOXY1과 DC1 사이의 이름 확인 및 네트워크 통신을 확인하려면 **ping dc1.corp.contoso.com** 명령을 실행하고 4개의 응답이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="0f1bc-148">다음으로, PROXY1의 Windows PowerShell 프롬프트에 다음 명령을 사용하여 PROXY1 가상 머신을 CORP 도메인에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="0f1bc-149">로컬 컴퓨터에서 다음 명령과 함께 PROXY1의 Azure PowerShell IP 주소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="0f1bc-p106">다음으로, 공용 DNS 공급자를 사용하고, **Write-Host** 명령에 의해 표시되는 IP 주소로 확인되는 **fs.testlab.**\<*your DNS domain name*>에 대한 새 공용 DNS A 레코드를 만듭니다. **fs.testlab.**\<*your DNS domain name*>을이제부터 *페더레이션 서비스 FQDN* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="0f1bc-154">다음으로, [Azure Portal](https://portal.azure.com)에서 CORP\\User1 자격 증명을 사용하여 DC1 가상 머신에 연결하고 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="0f1bc-155">이러한 명령은 Azure Virtual Network의 가상 머신이 내부 페더전 서비스 FQDN을 ADFS1의 개인 IP 주소로 확인할 수 있도록 내부 DNS A 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="0f1bc-156">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-156">Your resulting configuration looks like this:</span></span>
  
![웹 응용프로그램 프록시 서버가 Microsoft 365 테스트 환경에 대한 DirSync에 추가됨](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="0f1bc-158">4단계: 자체 서명된 인증서를 만들고 ADFS1 및 PROXY1을 구성</span><span class="sxs-lookup"><span data-stu-id="0f1bc-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="0f1bc-159">이 단계에서는 페더레이션 서비스 FQDN의 자체 서명된 디지털 인증서를 만들고 ADFS1 및 PROXY1을 AD FS 팜으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="0f1bc-160">먼저, [Azure Portal](https://portal.azure.com)에서 CORP\\User1 자격 증명을 사용하여 DC1 가상 머신에 연결하고 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="0f1bc-161">다음으로 DC1의 Windows PowerShell 명령 프롬프트에서 이 명령을 사용하여 AD FS 서비스 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="0f1bc-162">이 명령은 계정 암호를 입력하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="0f1bc-163">강력한 암호를 선택하고 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="0f1bc-164">이 단계와 5단계에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="0f1bc-p108">[Azure Portal](https://portal.azure.com)에서 CORP\\User1 자격 증명을 사용하여 ADFS1 가상 머신에 연결합니다. ADFS1에서 관리자 수준 Windows PowerShell 명령 프롬프트를 열고 페더레이션 서비스 FQDN을 입력한 후 다음 명령을 실행하여 자체 서명된 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="0f1bc-167">다음 단계를 사용하여 새 자체 서명된 인증서를 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="0f1bc-168">시작을 **선택하고** **mmc.exe** 를 입력한 다음 Enter **를 누르고 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="0f1bc-169">파일   >  **추가/제거를 끌기-in 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="0f1bc-170">추가 또는 끌기 **인에서** 사용 가능한 스냅인  목록에서 인증서를 두 번 클릭하고 컴퓨터 계정을 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="0f1bc-171">컴퓨터 **선택에서** 마친 **후** 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="0f1bc-172">트리 창에서 **인증서(로컬 컴퓨터) > 개인 > 인증서** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="0f1bc-173">페더ation Service FQDN이 있는 인증서를 선택하고 보류(또는 마우스 오른쪽 단추 클릭)를 선택하고 모든 작업을 선택한 다음 내보내기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="0f1bc-174">시작 **페이지에서** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="0f1bc-175">개인 키 **내보내기 페이지에서** 예를 **선택하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="0f1bc-176">파일 **내보내기 형식 페이지에서** **확장된** 모든 속성 내보내기 를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="0f1bc-177">보안 **페이지에서** 암호를 **선택하고** 암호 및  암호 확인에 **암호를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="0f1bc-178">**내보낼 파일 페이지에서** 찾아보기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="0f1bc-179">**C: \\ Certs** 폴더로 이동합니다. 파일 이름에 **SSL을** **입력한** 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="0f1bc-180">**내보낼 파일 페이지에서** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="0f1bc-181">인증서 **내보내기 마법사 완료 페이지에서** 마친 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="0f1bc-182">메시지가 표시될 때 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="0f1bc-183">다음으로, ADFS1의 Windows PowerShell 명령 프롬프트에서 다음 명령을 사용하여 AD FS 서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="0f1bc-184">설치가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="0f1bc-185">다음으로, 다음 단계에 따라 AD FS 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="0f1bc-186">시작 **을** 선택한 다음 서버 관리자 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="0f1bc-187">서버 관리자의 트리 창에서 **AD FS 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="0f1bc-188">맨 위에 있는 도구 모음에서 주황색 주의 기호를 선택한 다음 이 서버에서 페더링 서비스 구성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="0f1bc-189">Active  Directory Federation Services 구성 마법사의 시작 페이지에서 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="0f1bc-190">AD **커넥트** 페이지에서 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="0f1bc-191">**서비스 속성 지정** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="0f1bc-192">**SSL 인증서의** 경우 아래쪽 화살표를 선택한 다음 페더임 서비스 FQDN의 이름을 사용하여 인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="0f1bc-193">**페더ation Service 표시 이름에** 소설 조직의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="0f1bc-194">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="0f1bc-195">서비스 계정 **지정 페이지에서** 계정 **이름에 대해** **선택을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="0f1bc-196">사용자 **또는 서비스 계정 선택에서** **ADFS-Service를 입력하고** 이름 **확인을** 선택한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="0f1bc-197">계정 **암호에서** ADFS-Service 암호를 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="0f1bc-198">구성 데이터베이스 **지정 페이지에서** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="0f1bc-199">검토 **옵션 페이지에서** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="0f1bc-200">사전 검사 **페이지에서** 구성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="0f1bc-201">결과 **페이지에서** 닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="0f1bc-202">시작을 **선택하고** 전원 아이콘을 선택하고 다시 **시작을** 선택한 다음 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="0f1bc-203">[Azure Portal](https://portal.azure.com)에서 CORP\\User1 계정 자격 증명을 사용하여 PROXY1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="0f1bc-204">그런 후 다음 단계를 사용하여 **PROXY1과 APP1 모두** 에 자체 서명된 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="0f1bc-205">시작을 **선택하고** **mmc.exe** 를 입력한 다음 Enter **를 누르고 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="0f1bc-206">파일 **> 추가/제거를 끌기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="0f1bc-207">추가 또는 끌기 **인에서** 사용 가능한 스냅인  목록에서 인증서를 두 번 클릭하고 컴퓨터 계정을 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="0f1bc-208">컴퓨터 **선택에서** 마친 **후** 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="0f1bc-209">트리 창에서 **인증서(로컬 컴퓨터)** 개인  >    >  **인증서를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="0f1bc-210">개인 을 선택하고 보류(또는 마우스 오른쪽 단추 **클릭)를 선택하고** 모든 작업을 선택한 다음 가져오기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="0f1bc-211">시작 **페이지에서** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="0f1bc-212">가져올 **파일 페이지에서** **\\ \\ adfs1 \\ certs \\ ssl.pfx를** 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="0f1bc-213">개인 키 **보호 페이지에서** 암호 에 인증서 암호를 **입력하고** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="0f1bc-214">인증서 **저장소 페이지에서** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="0f1bc-215">완료 **페이지에서** 마친 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="0f1bc-216">인증서 **저장소 페이지에서** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="0f1bc-217">메시지가 표시될 때 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="0f1bc-218">트리 창에서 **인증서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="0f1bc-219">인증서를 선택하고 보류(또는 마우스 오른쪽 단추 클릭)한 다음 복사를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="0f1bc-220">트리 창에서 신뢰할 수 있는 루트 인증 **기관** 인증서  >  **를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="0f1bc-221">설치된 인증서 목록 아래에 마우스 포인터를 이동하고, 마우스를 잡고(또는 마우스 오른쪽 단추 클릭) **붙여넣기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="0f1bc-222">관리자 수준 PowerShell 명령 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="0f1bc-223">설치가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="0f1bc-224">다음 단계를 사용하여 ADFS1을 해당 페더레이션 서버로 사용하도록 웹 응용 프로그램 프록시 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="0f1bc-225">시작 **을** 선택한 다음 서버 관리자 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="0f1bc-226">트리 창에서 원격 **액세스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="0f1bc-227">위쪽의 도구 모음에서 주황색 주의 기호를 선택한 다음 웹 응용 프로그램 프록시 **마법사 열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="0f1bc-228">웹 **응용** 프로그램 프록시 구성 마법사의 시작 페이지에서 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="0f1bc-229">**페더레이션 서버** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="0f1bc-230">**페더임 서비스 이름** 상자에 페더ation Service FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="0f1bc-231">사용자 **이름 상자에** **CORP \\ User1 을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="0f1bc-232">암호 **상자에** User1 계정의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="0f1bc-233">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="0f1bc-234">AD **FS 프록시** 인증서 페이지에서 아래쪽 화살표를 선택하고 페더ation Service FQDN이 있는 인증서를 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="0f1bc-235">확인 **페이지에서** 구성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="0f1bc-236">결과 **페이지에서** 닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="0f1bc-237">5단계: 페더레이션 ID에 대해 Microsoft 365를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="0f1bc-238">[Azure Portal](https://portal.azure.com)에서 CORP\\User1 계정 자격 증명을 사용하여 APP1 가상 머신에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="0f1bc-239">다음 단계를 사용하여 페더레이션 인증을 위해 Azure AD Connect 및 Microsoft 365 구독을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="0f1bc-240">데스크톱에서 **Azure AD Connect** 를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="0f1bc-241">Azure AD 커넥트 시작 **페이지에서 구성을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="0f1bc-242">추가 **작업 페이지에서** 사용자 로그인 변경을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="0f1bc-243">Azure **AD 커넥트** 페이지에서 전역 관리자 계정 이름 및 암호를 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="0f1bc-244">사용자 **로그인 페이지에서** **AD FS와의** 페더ation을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="0f1bc-245">AD **FS 팜** 페이지에서 기존 **AD FS** 팜 사용을 선택하고  서버 이름 상자에 **ADFS1을** 입력한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="0f1bc-246">서버 자격 증명을 입력하라는 메시지가 표시될 때 CORP User1 계정의 자격 증명을 입력한 다음 \\ 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="0f1bc-247">도메인 **관리자** 자격 증명 페이지의 사용자 이름 상자에 **CORP \\ User1을** 입력하고 암호 상자에 계정 암호를 **입력한** 후 다음 을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="0f1bc-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="0f1bc-248">AD **FS** 서비스 계정 페이지의 도메인 사용자 이름 상자에  **CORP \\ ADFS-Service를** 입력하고 도메인 사용자 암호 상자에 계정 암호를 입력한 후 다음 을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="0f1bc-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="0f1bc-249">Azure **AD 도메인** 페이지의 도메인에서 **이전에** 1단계에서 생성하여 구독에 추가한 도메인의 이름을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="0f1bc-250">구성 **준비 완료 페이지에서** 구성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="0f1bc-251">설치 **완료 페이지에서** 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="0f1bc-252">인트라넷 및 인터넷 구성이 모두 확인되었음을 나타내는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="0f1bc-253">설치 **완료 페이지에서** 끝내기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="0f1bc-254">페더레이션 인증이 작동하는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="0f1bc-255">로컬 컴퓨터에서 브라우저의 새 개인 인스턴스를 열고 [https://admin.microsoft.com](https://admin.microsoft.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="0f1bc-256">로그인 자격 증명의 경우 **를** \<*the domain created in Phase 1*> user1@.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="0f1bc-257">예를 들어 테스트 도메인이 testlab.contoso.com **경우**"user1@testlab.contoso.com"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="0f1bc-258">Tab 키를 **누르거나** 사용자가 Microsoft 365 리디렉션하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="0f1bc-259">이제 연결이 **비공개가 아닌 페이지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="0f1bc-260">데스크톱 컴퓨터에서 확인할 수 없는 자체 서명된 인증서를 ADFS1에 설치한 경우 이 인증서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="0f1bc-261">페더타 인증의 프로덕션 배포에서는 신뢰할 수 있는 인증 기관의 인증서를 사용하며 사용자에게는 이 페이지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="0f1bc-262">연결이 **비공개가 아 않습니다. 페이지에서** 고급 **을** 선택하고 **계속을 선택합니다. \<*your federation service FQDN*>**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="0f1bc-263">가상의 조직 이름이 표시된 페이지에서 다음을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="0f1bc-264">이름: **CORP\\User1**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="0f1bc-265">User1 계정에 대한 암호</span><span class="sxs-lookup"><span data-stu-id="0f1bc-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="0f1bc-266">**Microsoft Office 홈** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="0f1bc-p112">이 절차에서는 평가판 구독이 DC1에 호스트된 AD DS corp.contoso.com 도메인과 페더레이션되는 방법을 보여줍니다. 다음은 인증 프로세스의 기본 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="0f1bc-269">1단계에서 만든 페더레이션 도메인을 로그인 계정 이름 내에서 사용할 경우 Microsoft 365는 페더레이션 서비스 FQDN 및 PROXY1으로 브라우저를 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="0f1bc-270">PROXY1은 가상의 회사 로그인 페이지를 로컬 컴퓨터로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="0f1bc-271">CORP\\User1 및 암호를 PROXY1으로 보내면 ADFS1로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="0f1bc-272">ADFS1은 DC1을 사용하여 CORP\\User1의 유효성을 검사하고 로컬 컴퓨터로 보안 토큰을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="0f1bc-273">로컬 컴퓨터가 Microsoft 365로 보안 토큰을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="0f1bc-274">Microsoft 365는 보안 토큰이 ADFS1에서 생성되었는지 확인하고 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="0f1bc-p113">이제 평가판 구독이 페더레이션 인증으로 구성됩니다. 고급 인증 시나리오에 대해 이 개발/테스트 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="0f1bc-277">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0f1bc-277">Next step</span></span>

<span data-ttu-id="0f1bc-278">Azure에서 배포할 수 있는 프로덕션 준비 고가용성 페더니트 인증을 배포할 준비가 Microsoft 365 Azure에서 고가용성 페더 Microsoft 365 [배포를 참조하세요.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)</span><span class="sxs-lookup"><span data-stu-id="0f1bc-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
