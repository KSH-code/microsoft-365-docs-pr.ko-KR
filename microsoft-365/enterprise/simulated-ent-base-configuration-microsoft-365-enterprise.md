---
title: Microsoft 365의 시뮬레이이트된 엔터프라이즈 기반 구성
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
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
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈용 테스트를 위한 시뮬레이트된 Microsoft 365 환경을 만들 수 있습니다.
ms.openlocfilehash: e3576c5d7e1a00069dd5dd46d1b1e6063da217bf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187899"
---
# <a name="the-simulated-enterprise-base-configuration"></a>시뮬레이트된 엔터프라이즈 기본 구성

*이 테스트 랩 가이드는 엔터프라이즈 및 엔터프라이즈용 Microsoft 365 둘 다에 사용할 Office 365 Enterprise 있습니다.*

이 문서에서는 다음을 포함하는 엔터프라이즈용 Microsoft 365 간소화된 환경을 만드는 방법을 설명합니다.

- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network의 3개의 가상 머신(DC1, APP1 및 CLIENT1)으로 구성됩니다.
 
![시뮬레이트된 엔터프라이즈 기본 구성입니다.](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

간소화된 테스트 환경을 만들 때에는 다음 두 단계가 필요합니다.
- [1단계: 시뮬레이트된 인트라넷 만들기](#phase-1-create-a-simulated-intranet)
- [2단계: Microsoft 365 E5 구독 만들기](#phase-2-create-your-microsoft-365-e5-subscription)

결과 환경을 사용하여 추가 테스트 랩 가이드를 [](https://www.microsoft.com/microsoft-365/enterprise) 사용하여 엔터프라이즈용 Microsoft 365 [](m365-enterprise-test-lab-guides.md) 기능을 테스트할 수 있습니다.

![Microsoft 클라우드용 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-create-a-simulated-intranet"></a>1단계: 시뮬레이트된 인트라넷 만들기

이 단계에서는 AD DS(Active Directory 도메인 서비스) 도메인 컨트롤러, 응용 프로그램 서버 및 클라이언트 컴퓨터를 포함하는 Azure 인프라 서비스에 시뮬레이트된 인트라넷을 구축합니다.

이러한 컴퓨터를 엔터프라이즈용 추가 테스트 랩 Microsoft 365 사용하여 하이브리드 ID [및](m365-enterprise-test-lab-guides.md) 기타 기능을 구성하고 보여줄 것입니다.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>방법 1: Azure Resource Manager 템플릿으로 시뮬레이트된 인트라넷 만들기

이 방법에서는 Azure Resource Manager 템플릿을 사용하여 시뮬레이트된 인트라넷을 빌드합니다. Azure Resource Manager 템플릿에는 Azure 네트워킹 인프라, 가상 컴퓨터 및 해당 구성을 만드는 모든 지침이 포함되어 있습니다.

서식 파일을 배포하기 전에 서식 파일 [README](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) 페이지를 읽고 다음 정보를 준비합니다.

- 테스트 환경의 공용 DNS 도메인 이름(testlab. \<*your public domain*> ) 사용자 지정 배포 페이지의 **도메인 이름** 필드에 이 이름을 **입력합니다.**
- 가상 머신의 공용 IP 주소 URL에 대한 DNS 레이블 접두사입니다. **사용자 지정 배포** 페이지의 **DNS 레이블 접두사** 필드에 이 레이블을 입력해야 합니다.

지침을 읽은 후 템플릿 [README](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) 페이지에서 **Azure에** 배포를 선택하여 시작할 수 있습니다.

>[!Note]
>Azure Resource Manager 템플릿으로 작성된 시뮬레이트된 인트라넷에는 유료 Azure 구독이 필요합니다.

템플릿이 완료되면 구성은 다음과 같습니다.

![Azure 인프라 서비스의 시뮬레이트된 인트라넷](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>방법 2: Azure PowerShell로 시뮬레이트된 인트라넷 만들기

이 방법에서는 Windows PowerShell 및 Azure PowerShell 모듈을 사용하여 네트워킹 인프라, 가상 머신 및 해당 구성을 만듭니다.

PowerShell을 통해 한 번에 하나의 단계씩 Azure 인프라의 요소를 만들려는 경우 이 방법을 사용합니다. Azure에서 다른 가상 머신을 직접 배포하기 위해 PowerShell 명령 블록을 사용자 지정할 수 있습니다.

#### <a name="step-1-create-dc1"></a>1단계: DC1 만들기

이 단계에서는 Azure Virtual Network를 만들고 AD DS 도메인의 도메인 컨트롤러인 가상 컴퓨터 DC1을 추가합니다.

먼저, 로컬 컴퓨터에서 Windows PowerShell 명령 프롬프트를 시작합니다.
  
> [!NOTE]
> 다음 명령 집합은 최신 버전의 Azure PowerShell을 사용합니다. [Azure PowerShell cmdlet으로 시작](/powershell/azureps-cmdlets-docs/)을 참조하세요. 
  
다음 명령을 사용하여 Azure 계정에 로그인합니다.
  
```powershell
Connect-AzAccount
```

다음 명령을 사용하여 구독 이름을 가져옵니다.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Azure 구독을 설정합니다. 앵글 괄호("<" 및 ">")를 포함하여 인용 부호 안에 있는 모든 것을 올바른 이름으로 바칭합니다.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

다음으로 시뮬레이트된 엔터프라이즈 테스트 랩에 대한 새 리소스 그룹을 만듭니다. 고유한 리소스 그룹 이름을 확인하려면 이 명령을 사용하여 기존 리소스 그룹을 나열합니다.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

이러한 명령을 사용하여 새 리소스 그룹을 만듭니다. 괄호를 포함하여 인용 부호 안에 있는 모든 것을 올바른 이름으로 바칭합니다.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

그런 다음 시뮬레이트된 엔터프라이즈 환경의 회사 네트워크 서브넷을 호스팅할 TestLab 가상 네트워크를 만들고 네트워크 보안 그룹으로 보호합니다. 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
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

다음으로, DC1 가상 머신을 만들고 **testlab.**\<your public domain> AD DS 도메인에 대한 도메인 컨트롤러와 TestLab 가상 네트워크의 가상 머신에 대한 DNS 서버로 구성합니다. 예를 들어 공용 도메인 이름이 **<span>contoso</span>.com** 이면 DC1 가상 머신은 **<span>testlab</span>.contoso.com** 에 대한 도메인 컨트롤러가 됩니다.
  
DC1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
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

DC1의 로컬 관리자 계정에 대한 사용자 이름과 암호를 입력하라는 메시지가 표시됩니다. 강력한 암호를 사용하고 이름 및 암호를 안전한 위치에 보관합니다.
  
다음으로 DC1 가상 컴퓨터에 연결합니다.
  
1. Azure [Portal에서](https://portal.azure.com)리소스 그룹을 선택하고 **> <** 리소스 그룹의 이름 ***_***> > _ DC1  >  커넥트.
    
2. 열린 창에서 **RDP 파일 다운로드를 선택합니다.** 다운로드한 DC1.rdp 파일을 열고 를 **커넥트.**
    
3. DC1 로컬 관리자 계정 이름을 지정합니다.
    
   - Windows 7:
    
     사용자 **Windows 보안** 다른 계정 사용을 **선택합니다.** 사용자 **이름 에** **\\ DC1** 로컬 관리자 계정 < *이름*>.
    
   - Windows 8.1 또는 Windows 10:
    
     추가 **Windows 보안** 대화 상자에서 추가 선택 을 선택한 다음 다른 계정 사용을 **선택합니다.** 사용자 **이름 에** **\\ DC1** 로컬 관리자 계정 < *이름*>.
    
4. **암호에서** 로컬 관리자 계정의 암호를 입력한 다음 확인 을 **선택합니다.**
    
5. 메시지가 표시될 때 예를 **선택합니다.**
    
다음으로 DC1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 사용하여 추가 데이터 디스크를 드라이브 문자 F:의 새로운 볼륨으로 추가합니다.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

그런 다음, DC1을 **testlab.**\<*your public domain*> 도메인에 대한 도메인 컨트롤러 및 DNS 서버로 구성합니다. 공용 도메인 이름을 지정하고 괄호를 제거한 다음 DC1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
안전 모드 관리자 암호를 지정해야 합니다. 이 암호를 안전한 장소에 저장합니다.
  
이러한 명령은 완료하는 데 몇 분 정도 걸릴 수 있습니다.
  
DC1이 다시 시작되면 DC1 가상 머신에 다시 연결합니다.
  
1. Azure [Portal에서](https://portal.azure.com)리소스  그룹 을  > <**DC1**> > 그룹  >  **커넥트.**
    
2. 다운로드된 DC1.rdp 파일을 실행한 다음 를 **커넥트.**
    
3. 에서 **Windows 보안** 다른 계정 **사용을 선택합니다.** 사용자 **이름에** **TESTLAB \\** 로컬 관리자 계정 < *이름 입력을>.*
    
4. 암호 **상자에** 로컬 관리자 계정의 암호를 입력한 다음 확인 을 **선택합니다.**
    
5. 메시지가 표시될 때 예를 **선택합니다.**
    
다음으로, TESTLAB 도메인 구성원 컴퓨터에 로그인할 때 사용할 사용자 계정을 Active Directory에 생성합니다. 관리자 수준의 명령 프롬프트에서 Windows PowerShell 실행합니다.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

이 명령은 User1 계정 암호를 입력하라는 메시지를 표시합니다. 이 계정은 모든 TESTLAB 도메인 구성원 컴퓨터에 대한 원격 데스크톱 연결에 사용 따라서 강력한 암호를 선택 합니다. User1 계정 암호를 기록하고 안전한 위치에 저장합니다.
  
다음으로, 새 User1 계정을 도메인, 엔터프라이즈 및 스키마 관리자로 구성합니다. 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

DC1과의 원격 데스크톱 세션을 닫은 후 TESTLAB\\User1 계정을 사용하여 다시 연결합니다.
  
다음으로, Ping 도구에 대한 트래픽을 허용하려면 관리자 수준의 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

현재 구성은 다음과 같습니다.
  
![시뮬레이트된 엔터프라이즈 기본 구성의 1단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>2단계: APP1 구성

이 단계에서는 처음에 웹 및 파일 공유 서비스를 제공하는 응용 프로그램 서버인 APP1을 만들고 구성합니다.

APP1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 명령 프롬프트에서 다음 명령을 실행합니다.
  
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

다음으로, APP1 로컬 관리자 계정 이름과 암호를 사용하여 APP1 가상 머신에 연결하고 Windows PowerShell 명령 프롬프트를 엽니다.
  
APP1와 DC1 사이의 이름 확인과 네트워크 통신을 확인하려면 **ping dc1.testlab.**\<*your public domain name*>을(를) 실행하고 응답이 4개인지 확인합니다.
  
다음으로, Windows PowerShell 프롬프트에 다음 명령을 사용하여 APP1 가상 머신을 TESTLAB 도메인에 가입합니다.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

**Add-Computer** 명령을 실행한 후 TESTLAB User1 도메인 계정 자격 \\ 증명을 제공해야 합니다.
  
APP1을 다시 시작한 후에 TESTLAB\\User1 계정을 사용하여 연결한 후 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.
  
다음으로, APP1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 사용하여 APP1을 웹 서버로 만듭니다.
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

그런 후 다음 PowerShell 명령을 사용하여 APP1의 폴더 내에 공유 폴더 및 텍스트 파일을 만듭니다.
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

현재 구성은 다음과 같습니다.
  
![시뮬레이트된 엔터프라이즈 기본 구성의 2단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>3단계: CLIENT1 구성

이 단계에서는 인트라넷에서 전형적인 랩톱, 태블릿 또는 데스크톱 컴퓨터의 역할을 하는 CLIENT1을 만들고 구성합니다.

> [!NOTE]  
> 다음 명령 집합은 Windows Server 2016 Datacenter를 실행하는 CLIENT1을 만듭니다. 이 작업은 모든 유형의 Azure 구독에서 수행할 수 있습니다. Visual Studio 기반 Azure 구독이 있는 경우 [Azure Portal](https://portal.azure.com)을 사용하여 Windows 10이 실행되는 CLIENT1을 만들 수 있습니다.
  
CLIENT1에 대한 Azure Virtual Machine을 만들하려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 명령 프롬프트에서 다음 명령을 실행합니다.
  
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

다음으로, CLIENT1 로컬 관리자 계정 이름과 암호를 사용하여 CLIENT1 가상 머신에 연결하고 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.
  
APP1와 DC1 사이의 이름 확인과 네트워크 통신을 확인하려면 Windows PowerShell 명령 프롬프트에서 **ping dc1.testlab.**\<*your public domain name*> 명령을 실행하고 응답이 4개인지 확인합니다.
  
다음으로, Windows PowerShell 프롬프트에 다음 명령을 사용하여 CLIENT1 가상 머신을 TESTLAB 도메인에 가입합니다.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

**Add-Computer** 명령을 실행한 후 TESTLAB\\User1 도메인 계정 자격 증명을 제공해야 합니다.
  
CLIENT1을 다시 시작한 후에 TESTLAB\\User1 계정 이름 및 암호를 사용하여 연결한 후 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.
  
그런 후 CLIENT1에서 APP1의 웹 및 파일 공유 리소스에 액세스할 수 있는지 확인합니다.
  
1. 서버 관리자의 트리 창에서 로컬 서버 **를 선택합니다.**
    
2. **CLIENT1의 속성에서** IE **보안 강화** 구성 옆에 **있는 을 선택합니다.**
    
3. 보안 **Internet Explorer** 에서 관리자 및  사용자에  대해 끄기 를 선택하고 확인 을 **선택합니다.**
    
4. 시작 화면에서 를 **Internet Explorer** 를 선택한 다음 확인 을 **선택합니다.**
    
5. 주소 표시줄에 **http <span>://</span>app1.testab.** 를 입력한 \<*your public domain name*> **/** 다음 **Enter를 입력합니다.** APP1에 대한 기본 인터넷 정보 서비스 웹 페이지가 표시됩니다.
    
6. 데스크톱 작업 표시줄에서 파일 탐색기 아이콘을 선택합니다.
    
7. 주소 표시줄에 **\\ \\ app1 Files 를 \\ 입력한** 다음 Enter 를 **입력합니다.** Files 공유 폴더의 내용이 있는 폴더 창이 표시됩니다.
    
8. **Files** 공유 폴더 창에서 **Example.txt** 파일을 두 번 클릭합니다. Example.txt 파일의 내용을 표시됩니다.
    
9. **example.txt - 메모장** 과 **Files** 공유 폴더 창을 닫습니다.
    
현재 구성은 다음과 같습니다.
  
![시뮬레이트된 엔터프라이즈 기본 구성의 3단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>2단계: Microsoft 365 E5 구독 만들기

이 단계에서는 프로덕션 구독과는 별개인 새롭고 일반적인 Azure AD 테넌트를 사용하는 새 Microsoft 365 E5 구독을 만듭니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.

- Microsoft 365 E5 평가판 구독을 사용 합니다.

  Microsoft 365 E5 평가판 구독 기간은 30일로, 60일까지 쉽게 연장할 수 있습니다. 평가판 구독이 만료되면 유료 구독으로 전환하거나 새 평가판 구독을 만들어야 합니다. 새 평가판 구독을 만든다는 것은 복잡한 시나리오를 포함하는 구성을 벗어난다는 것을 의미합니다.  

- 적은 수의 라이선스로 Microsoft 365 E5의 별도 프로덕션 구독을 사용합니다.

  이 경우 추가 비용이 들지만 만료되지 않는 작업 테스트 환경이 확보됩니다. 기능, 구성 및 시나리오를 시도할 수 있습니다. 개념 증명, 피어 및 관리에 대한 데모, 응용 프로그램 개발 및 테스트를 위해 장기적으로 동일한 테스트 환경을 사용할 수 있습니다. 이 방법을 사용하는 것이 좋습니다.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Office 365 E5 평가판 구독 등록

Azure Portal에서 CORP\User1 계정을 사용하여 CLIENT1에 연결합니다.

새 Office 365 E5 평가판 구독을 만들려면 간단한 기본 구성 테스트 랩 가이드의 [1단계 ](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription)에 있는 지침을 수행하십시오.

새 Office 365 E5 평가판 구독을 구성하려면 간단한 기본 구성 테스트 랩 가이드의 [2단계 ](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription)에 있는 지침을 수행하십시오.

#### <a name="using-an-office-365-e5-test-environment"></a>Office 365 E5 테스트 환경 사용

테스트 환경만 Office 365 경우 이 문서의 나머지 내용을 읽을 필요가 없습니다.

Microsoft 365 및 Office 365 테스트 랩 가이드에 Microsoft 365 테스트 랩 가이드를 [참조하세요.](m365-enterprise-test-lab-guides.md)

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Microsoft 365 E5 평가판 구독 추가

Microsoft 365 E5 평가판 구독을 추가하고 사용자 계정을 라이선스로 구성하려면 간단한 기본 구성 테스트 랩 [가이드의 3단계에](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) 있는 지침을 수행하세요.

  
## <a name="results"></a>결과

이제 테스트 환경에는 다음이 구현됩니다.
  
- Microsoft 365 E5 평가판 구독.
- 모든 적절한 사용자 계정이 Microsoft 365 E5를 사용할 수 있습니다.
- 시뮬레이션되고 단순화된 인트라넷.
    
최종 구성은 다음과 같습니다.
  
![시뮬레이트된 엔터프라이즈 기본 구성의 2단계](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
이제 엔터프라이즈용 에디터스 에디터의 추가 [기능을 Microsoft 365 준비가 완료되었습니다.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>다음 단계

다음과 같은 추가 테스트 랩 가이드 집합에 대해 알아봅니다.
  
- [ID](m365-enterprise-test-lab-guides.md#identity)
- [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [정보 보호](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)