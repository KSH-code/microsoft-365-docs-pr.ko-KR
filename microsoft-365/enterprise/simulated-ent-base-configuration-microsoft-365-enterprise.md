---
title: Microsoft 365의 시뮬레이이트된 엔터프라이즈 기반 구성
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 이 테스트 랩 가이드를 사용하여 Microsoft 365 Enterprise 테스트를 위한 시뮬레이트된 엔터프라이즈 테스트 환경을 만듭니다.
ms.openlocfilehash: 907bec83ac4ad820ec1cb710209614636a4f54e8
ms.sourcegitcommit: 1b77b699b8e23df8b98530dfad3a29b4aaa0753c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2019
ms.locfileid: "33867988"
---
# <a name="the-simulated-enterprise-base-configuration"></a>시뮬레이트된 엔터프라이즈 기본 구성

이 문서에서는 다음을 포함하는 Microsoft 365 Enterprise의 간소화된 환경을 만들기 위한 단계별 지침을 제공합니다.

- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network의 3가지 가상 머신(DC1, APP1 및 CLIENT1)으로 구성됩니다.
 
![시뮬레이트된 엔터프라이즈 기본 구성](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

추가 [테스트 랩 가이드](m365-enterprise-test-lab-guides.md)를 진행하고 결과 환경을 사용하거나 직접 구성한 환경을 사용하여 [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)의 특성과 기능을 테스트할 수 있습니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-create-a-simulated-intranet"></a>1단계: 시뮬레이트된 인트라넷 만들기

이 단계에서는 AD DS(Active Directory Domain Services) 도메인 컨트롤러, 응용프로그램 서버, 클라이언트 컴퓨터를 포함하는 Azure 인프라 서비스에 시뮬레이트된 인트라넷을 만듭니다. 

이 컴퓨터를 추가 [Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)에서 이 컴퓨터를 사용하여 하이브리드 ID 및 기타 기능을 구성하고 보여줍니다.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>방법 1: Azure Resource Manager 템플릿으로 시뮬레이트된 인트라넷 만들기

이 방법에서는 ARM(Azure Resource Manager) 템플릿을 사용하여 시뮬레이트된 인트라넷을 만듭니다. ARM 템플릿에는 Azure 네트워킹 인프라, 가상 머신 및 해당 구성을 만드는 모든 인프라가 포함됩니다.

템플릿을 배포하기 전에 [템플릿 추가 정보 페이지](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)를 읽고 다음 정보를 준비합니다.

- 테스트 환경의 공용 DNS 도메인 이름(testlab.\<your public domain>)입니다. **사용자 지정 배포** 페이지의 **도메인 이름 필드**에 이 이름을 입력해야 합니다.
- 가상 머신의 공용 IP 주소 URL에 대한 DNS 레이블 접두사입니다. **사용자 지정 배포** 페이지의 **DNS 레이블 접두사** 필드에 이 레이블을 입력해야 합니다.

지침을 읽은 후 [템플릿 추가 정보 페이지](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)에서 **Azure로 배포**를 클릭하여 시작합니다.

>[!Note]
>ARM 템플릿에서 만든 시뮬레이트된 인트라넷은 유료 Azure 구독이 있어야 합니다.
>

템플릿이 완료된 후 구성입니다.

![Azure 인프라 서비스의 시뮬레이트된 인트라넷](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>방법 2: Azure PowerShell로 시뮬레이트된 인트라넷 만들기

이 방법에서는 Windows PowerShell 및 Azure PowerShell 모듈을 사용하여 네트워킹 인프라, 가상 머신 및 해당 구성을 만듭니다.

PowerShell을 통해 한 번에 하나의 단계씩 Azure 인프라의 요소를 만들려는 경우 이 방법을 사용합니다. Azure에서 다른 가상 머신을 직접 배포하기 위해 PowerShell 명령 블록을 사용자 지정할 수 있습니다.

#### <a name="step-1-create-dc1"></a>1단계: DC1 만들기

이 단계에서는 Azure Virtual Network를 만들고, AD DS 도메인에 대한 도메인 컨트롤러인 가상 머신 DC1을 추가합니다.

먼저, 로컬 컴퓨터에서 Windows PowerShell 명령 프롬프트를 시작합니다.
  
> [!NOTE]
> 다음 명령 집합은 최신 버전의 Azure PowerShell을 사용합니다. [Azure PowerShell cmdlet으로 시작](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)을 참조하세요. 
  
다음 명령을 사용하여 Azure 계정에 로그인합니다.
  
```
Connect-AzAccount
```

다음 명령을 사용하여 구독 이름을 가져옵니다.
  
```
Get-AzSubscription | Sort Name | Select Name
```

Azure 구독을 설정합니다. < 및 > 문자를 포함하여 따옴표 안에 있는 모든 것을 올바른 이름으로 바꿉니다.
  
```
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

다음으로 시뮬레이트된 엔터프라이즈 테스트 랩에 대한 새 리소스 그룹을 만듭니다. 고유한 리소스 그룹 이름을 확인하려면 이 명령을 사용하여 기존 리소스 그룹을 나열합니다.
  
```
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

이러한 명령을 사용하여 새 리소스 그룹을 만듭니다. < 및 > 문자를 포함하여 따옴표 안에 있는 모든 내용을 올바른 이름으로 바꿉니다.
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

다음으로, 시뮬레이트된 엔터프라이즈 환경의 Corpnet 서브넷을 호스트하는 테스트 랩 가상 네트워크를 만들고 네트워크 보안 그룹을 사용하여 보호합니다. 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
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

다음에는 DC1 가상 머신을 만들고 **testlab.**\<공용 도메인>AD DS 도메인 및 TestLab 가상 네트워크의 가상 머신에 대한 DNS 서버의 도메인 컨트롤러로 구성합니다. 예를 들어 공용 도메인 이름이 **<span>contoso</span>.com**이면 DC1 가상 머신은 **<span>testlab</span>.contoso.com**에 대한 도메인 컨트롤러가 됩니다.
  
DC1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A1
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
  
다음으로, DC1 가상 머신에 연결합니다.
  
1. [Azure Portal](https://portal.azure.com)에서 **리소스 그룹 >** [새 리소스 그룹의 이름] **> DC1 > 연결**을 클릭합니다.
    
2. 열려 있는 창에서 **RDP 파일 다운로드**를 클릭합니다. 다운로드된 DC1.rdp 파일을 열고 **연결**을 클릭합니다.
    
3. DC1 로컬 관리자 계정 이름을 지정합니다.
    
   - Windows 7:
    
     **Windows 보안** 대화 상자에서 **다른 계정 사용**을 클릭합니다. **사용자 이름**에서 **DC1\\**[로컬 관리자 계정 이름]을 입력합니다.
    
   - Windows 8.1 또는 Windows 10:
    
     **Windows 보안** 대화 상자에서 **기타 선택 사항**을 클릭하고 **다른 계정 사용**을 클릭합니다. **사용자 이름**에서 **DC1\\**[로컬 관리자 계정 이름]을 입력합니다.
    
4. **암호**에서 로컬 관리자 계정의 암호를 입력하고 **확인**을 클릭합니다.
    
5. 메시지가 표시되면 **예**를 클릭합니다.
    
다음으로 DC1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 사용하여 추가 데이터 디스크를 드라이브 문자 F:의 새로운 볼륨으로 추가합니다.
  
```
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

그런 후 DC1을 **testlab.**\<공용 도메인 > 도메인에 대한 도메인 컨트롤러 및 DNS 서버로 구성합니다. 공용 도메인 이름을 지정하고 \< 및 > 문자를 제거한 후 DC1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
안전 모드 관리자 암호를 지정해야 합니다. 이 암호를 안전한 장소에 저장합니다.
  
이러한 명령은 완료하는 데 몇 분 정도 걸릴 수 있습니다.
  
DC1이 다시 시작되면 DC1 가상 머신에 다시 연결합니다.
  
1. [Azure Portal](https://portal.azure.com)에서 **리소스 그룹 >** [리소스 그룹 이름] **> DC1 > 연결**을 클릭합니다.
    
2. 다운로드된 DC1.rdp 파일을 실행하고 **연결**을 클릭합니다.
    
3. **Windows 보안**에서 **다른 계정 사용**을 클릭합니다. **사용자 이름**에서 **TESTLAB\\**[로컬 관리자 계정 이름]을 입력합니다.
    
4. **암호**에서 로컬 관리자 계정의 암호를 입력하고 **확인**을 클릭합니다.
    
5. 메시지가 표시되면 **예**를 클릭합니다.
    
다음으로, TESTLAB 도메인 구성원 컴퓨터에 로그인할 때 사용할 사용자 계정을 Active Directory에서 만듭니다. 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

이 명령은 User1 계정 암호를 묻는 메시지를 표시합니다. 이 계정은 모든 TESTLAB 도메인 구성원 컴퓨터에 대한 원격 데스크톱 연결에 사용되므로 강력한 암호를 선택합니다. User1 계정 암호를 기록한 후 안전한 위치에 보관합니다.
  
다음으로, 새 User1 계정을 도메인, 엔터프라이즈 및 스키마 관리자로 구성합니다. 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
$yourDomain="<your public domain>"
$domainName = "testlab"+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

DC1과의 원격 데스크톱 세션을 닫은 후 TESTLAB\\User1 계정을 사용하여 다시 연결합니다.
  
다음으로, Ping 도구에 대한 트래픽을 허용하려면 관리자 수준의 Windows PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

다음은 현재 구성입니다.
  
![시뮬레이트된 엔터프라이즈 기반 구성 1단계](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>2단계: APP1 구성

이 단계에서는 처음에 웹 및 파일 공유 서비스를 제공하는 응용 프로그램 서버인 APP1을 만들고 구성합니다.

APP1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

다음으로, APP1 로컬 관리자 계정 이름과 암호를 사용하여 APP1 가상 머신에 연결하고 Windows PowerShell 명령 프롬프트를 엽니다.
  
APP1과 DC1 사이의 이름 확인 및 네트워크 통신을 확인하려면 **ping dc1.testlab.**\<공용 도메인 이름> 명령을 실행하고 4개의 응답이 있는지 확인합니다.
  
다음으로, Windows PowerShell 프롬프트에 다음 명령을 사용하여 APP1 가상 머신을 TESTLAB 도메인에 가입합니다.
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

**Add-Computer** 명령을 실행한 후 TESTLAB\\User1 도메인 계정 자격 증명을 제공해야 합니다.
  
APP1을 다시 시작한 후에 TESTLAB\\User1 계정을 사용하여 연결한 후 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.
  
다음으로, APP1의 관리자 수준 Windows PowerShell 명령 프롬프트에서 다음 명령을 사용하여 APP1을 웹 서버로 만듭니다.
  
```
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

그런 후 다음 PowerShell 명령을 사용하여 APP1의 폴더 내에 공유 폴더 및 텍스트 파일을 만듭니다.
  
```
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

다음은 현재 구성입니다.
  
![시뮬레이트된 엔터프라이즈 기반 구성 2단계](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>3단계: CLIENT1 구성

이 단계에서는 인트라넷에서 전형적인 랩톱, 태블릿 또는 데스크톱 컴퓨터의 역할을 하는 CLIENT1을 만들고 구성합니다.

> [!NOTE]  
> 다음 명령 집합은 Windows Server 2016 Datacenter를 실행하는 CLIENT1을 만듭니다. 이 작업은 모든 유형의 Azure 구독에서 수행할 수 있습니다. Visual Studio 기반 Azure 구독이 있는 경우 [Azure Portal](https://portal.azure.com)을 사용하여 Windows 10이 실행되는 CLIENT1을 만들 수 있습니다. 
  
CLIENT1에 대한 Azure Virtual Machine을 만들려면 리소스 그룹의 이름을 입력하고 로컬 컴퓨터의 명령 프롬프트에서 다음 명령을 실행합니다.
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

다음으로, CLIENT1 로컬 관리자 계정 이름과 암호를 사용하여 CLIENT1 가상 머신에 연결하고 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.
  
CLIENT1과 DC1 사이의 이름 확인 및 네트워크 통신을 확인하려면 Windows PowerShell 명령 프롬프트에서 **ping dc1.testlab.**\<공용 도메인 이름> 명령을 실행하고 4개의 응답이 있는지 확인합니다.
  
다음으로, Windows PowerShell 프롬프트에 다음 명령을 사용하여 CLIENT1 가상 머신을 TESTLAB 도메인에 가입합니다.
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

**Add-Computer** 명령을 실행한 후 TESTLAB\\User1 도메인 계정 자격 증명을 제공해야 합니다.
  
CLIENT1을 다시 시작한 후에 TESTLAB\\User1 계정 이름 및 암호를 사용하여 연결한 후 관리자 수준 Windows PowerShell 명령 프롬프트를 엽니다.
  
그런 후 CLIENT1에서 APP1의 웹 및 파일 공유 리소스에 액세스할 수 있는지 확인합니다.
  
1. 서버 관리자의 트리 창에서 **로컬 서버**를 클릭합니다.
    
2. **CLIENT1에 대한 속성**에서 **IE 보안 강화 구성** 옆의 **켜기**를 클릭합니다.
    
3. **Internet Explorer 보안 강화 구성**에서 **관리자** 및 **사용자**에 대해 **끄기**를 클릭한 후 ** 확인**을 클릭합니다.
    
4. 시작 화면에서 **Internet Explorer**를 클릭하고 **확인**을 클릭합니다.
    
5. 주소 표시줄에 **http<span>://</span>app1.testab.**\<공용 도메인 이름>**/** 을 입력하고 Enter 키를 누릅니다. APP1에 대한 기본 인터넷 정보 서비스 웹 페이지가 표시됩니다.
    
6. 바탕 화면 작업 표시줄에서 파일 탐색기 아이콘을 클릭합니다.
    
7. 주소 표시줄에 **\\\\app1\\Files일**를 입력하고 Enter 키를 누릅니다. Files 공유 폴더의 내용이 포함된 폴더 창이 표시됩니다.
    
8. **Files** 공유 폴더 창에서 **Example.txt** 파일을 두 번 클릭합니다. Example.txt 파일의 내용을 표시됩니다.
    
9. **example.txt - 메모장**과 **Files** 공유 폴더 창을 닫습니다.
    
다음은 현재 구성입니다.
  
![시뮬레이트된 엔터프라이즈 기반 구성 3단계](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscriptions"></a>2단계: Microsoft 365 E5 구독 만들기

이 단계에서는 프로덕션 구독과는 별개인 새롭고 일반적인 Azure AD 테넌트를 사용하는 새 Microsoft 365 E5 구독을 만듭니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.

- Microsoft 365 E5 평가판 구독을 사용 합니다. 

  Microsoft 365 E5 평가판 구독 기간은 30일로, 60일까지 쉽게 연장할 수 있습니다. 평가판 구독이 만료되면 유료 구독으로 전환하거나 새 평가판 구독을 만들어야 합니다. 새 평가판 구독을 만든다는 것은 복잡한 시나리오를 포함하는 구성을 벗어난다는 것을 의미합니다.  
- 적은 수의 라이선스로 Microsoft 365 E5의 별도 프로덕션 구독을 사용합니다.

  이 경우 추가 비용이 발생하지만, 만료되지 않는 기능, 구성 및 시나리오를 사용해볼 수 있는 작업 테스트 환경을 보유하게 됩니다. 개념 증명, 피어 및 관리 부서에 데모 제공, 응용 프로그램 개발 및 테스트를 위해 장기간 동일한 테스트 환경을 사용할 수 있습니다. 이것이 권장되는 방법입니다.

### <a name="use-trial-subscriptions"></a>평가판 구독 사용

우선, [Office 365 개발/테스트 환경](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)의 2, 3단계의 세부 단계를 수행하여 경량의 Office 365 개발/테스트 환경을 만듭니다.

>[!Note]
>우리는 사용자의 Office 365의 평가판 구독을 생성하여 개발/테스트 환경에 사용자가 현재 보유하고 있는 유료 구독과 별도의 Azure AD 테넌트를 보유하게 합니다. 이러한 분리는 프로덕션 구독에 영향없이 테스트 테넌트의 사용자 및 그룹을 추가 및 제거할 수 있음을 의미합니다.
>

다음, Microsoft 365 E5 평가판 구독을 추가하고 전역 관리자 계정에 Microsoft 365 라이선스를 할당합니다.

1. 인터넷 브라우저의 개인 인스턴스를 사용하고 전역 관리자 계정 자격 증명으로 [http://admin.microsoft.com](http://admin.microsoft.com)의 Microsoft 365 관리 센터에 로그인합니다.
    
2. **Microsoft 365 관리 센터** 페이지에 있는 왼쪽 탐색 영역에서 **대금 청구 > 서비스 구매**를 차례로 클릭합니다.
    
3. **서비스 구매** 페이지에서, **Microsoft 365 E5** 항목을 찾습니다. 마우스 포인터를 가져간 후 **평가판 시작**을 클릭합니다.

4. **Microsoft 365 E5 평가판** 페이지에서 텍스트 또는 전화를 받도록 선택한 다음, 전화 번호를 입력하고, **문자 받기** 또는 **전화 받기**를 클릭합니다.

5. **주문 확인** 페이지에서 **지금 평가판 사용**을 클릭합니다.

6. **주문 접수** 페이지에서 **계속**을 클릭합니다.

7. Microsoft 365 관리 센터에서 **활성 사용자**를 클릭 한 다음 관리자 계정을 클릭합니다.

8. **제품 라이센스**에 대한 **편집**을 클릭합니다.

9. Office 365 Enterprise E5의 라이센스를 끄고 Microsoft 365 E5의 라이센스를 켭니다.

10. **저장 > 닫기 > 닫기**를 클릭합니다.

 다음, [Office 365 개발/테스트 환경](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)의 ***3단계를 완료한 경우,*** 다른 모든 계정(사용자 2, 사용자 3, 사용자 4 및 사용자 5)에 대해 이전 절차의 8 및 11단계를 반복합니다.
  
> [!NOTE]
> Microsoft 365 E5 평가판 구독은 30일입니다. 영구 테스트 환경의 경우 소수의 라이선스를 사용해서 이 평가판 구독을 유료 구독으로 전환합니다.
  
이제 테스트 환경에는 다음이 구현됩니다.
  
- Microsoft 365 E5 평가판 구독.
- 모든 해당 사용자 계정(전역 관리자만 또는 5개의 사용자 계정 모두)이 Microsoft 365 E5를 사용하도록 설정됩니다.
    
### <a name="results"></a>결과

이제 테스트 환경에는 다음이 구현됩니다.
  
- Microsoft 365 E5 평가판 구독.
- 모든 해당 사용자 계정(전역 관리자만 또는 5개의 사용자 계정 모두)이 Microsoft 365 E5를 사용하도록 설정됩니다.
    
다음은 최종 구성입니다.
  
![시뮬레이트된 엔터프라이즈 기반 구성 4단계](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
이제 [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)의 추가 기능을 사용해볼 준비가 되었습니다.
  
## <a name="next-steps"></a>다음 단계

다음과 같은 추가 테스트 랩 가이드 집합에 대해 알아봅니다.
  
- [ID](m365-enterprise-test-lab-guides.md#identity)
- [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [정보 보호](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
