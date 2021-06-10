---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 장치 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스에 대한 추가 장치 정보입니다.'
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861309"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 장치 정보

도이치클랜드 Microsoft 클라우드에 연결된 Azure AD 가입 및 등록된 장치는 9단계 및 10단계 이전으로 마이그레이션해야 합니다. 장치 마이그레이션은 장치 유형, 운영 체제 및 AAD 관계에 따라 다릅니다. 

## <a name="frequently-asked-questions"></a>자주하는 질문

**조직이 영향을 받는지 어떻게 알 수 있나요?**

관리자는 등록된 장치 또는 Azure AD에 가입된 장치가 있는지 `https://portal.microsoftazure.de` 여부를 확인해야 합니다. 조직에서 장치를 등록한 경우 영향을 받을 수 있습니다.

**사용자에게 어떤 영향이 있나요?**

등록된 장치의 사용자는 마이그레이션 [10단계가](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 완료되고 도이치란드 Microsoft 클라우드의 끝점을 사용하지 않도록 설정한 후에 더 이상 로그인할 수 없습니다.  

조직이 도이치란드 Microsoft 클라우드에서 연결이 끊어지기 전에 모든 장치가 전 세계 끝점에 등록되어 있도록 합니다.
  
**사용자가 언제 장치를 다시 등록하나요?**

[9단계가](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 완료된 후에만 장치를 등록을 등록을 해지하고 다시 등록하는 것은 성공에 중요합니다. 10단계가 시작되기 전에 다시 등록을 완료해야 합니다. 그렇지 않으면 장치에 대한 액세스 권한이 손실될 수 있습니다.

**마이그레이션 후 장치 상태를 복원하려면 어떻게 해야 합니까?**

Azure AD에 등록된 회사 소유의 Windows 디바이스의 경우 관리자는 원격으로 트리거된 워크플로를 통해 이전 장치 상태의 등록을 등록하지 않는 워크플로를 통해 이러한 디바이스의 마이그레이션을 관리할 수 있습니다.
  
Azure AD에 등록된 개인 Windows 장치를 비롯한 다른 모든 장치의 경우 최종 사용자는 이러한 단계를 수동으로 수행해야 합니다. Azure AD에 가입된 장치의 경우 사용자는 등록을 하지 않은 후 장치를 다시 등록하려면 로컬 관리자 계정이 필요합니다.

아래에서 장치 상태로 복원하는 방법에 대한 자세한 지침을 참조하세요. 
 
**모든 장치가 공용 클라우드에 등록되어 있는 것을 어떻게 알 수 있나요?**

장치가 공용 클라우드에 등록되어 있는지 확인하려면 Azure AD 포털에서 장치 목록을 내보내고 앱 스프레드시트로 Excel 합니다. 그런 다음 도이치랜드 [Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 클라우드와 별개의 마이그레이션 단계 후 _registeredTime_ 열을 사용하여 등록된 장치를 필터링합니다.

## <a name="additional-considerations"></a>추가 고려 사항
장치 등록은 테넌트 마이그레이션 후 비활성화되어 활성화하거나 사용하지 않도록 설정할 수 없습니다. 

Intune이 사용되지 않는 경우 구독에 로그인하고 다음 명령을 실행하여 옵션을 다시 활성화합니다.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**중요:** Intune 서비스 보안 주체는 상거래 마이그레이션 후 활성화됩니다. 이는 Azure AD 장치 등록의 활성화를 암시합니다. 마이그레이션 전에 Azure AD 장치 등록을 차단한 경우 Azure AD 포털에서 Azure AD 장치 등록을 다시 사용하지 않도록 설정하려면 PowerShell을 사용하여 Intune 서비스 계정을 사용하지 않도록 설정해야 합니다. 이 명령을 사용하여 Intune 서비스 주체는 Azure Active Directory PowerShell for Graph 있습니다.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Azure AD 가입
이는 디바이스에 Windows 10 적용됩니다. 

디바이스가 Azure AD에 가입된 경우 Azure AD에서 연결을 끊고 다시 연결해야 합니다. 

[![Azure AD 장치 Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


사용자가 디바이스의 관리자인 Windows 10 Azure AD에서 디바이스 등록을 등록을 해지하고 다시 가입할 수 있습니다. 관리자 권한이 없는 사용자는 이 컴퓨터의 로컬 관리자 계정 자격 증명이 필요합니다. 


관리자는 다음 구성 경로에 따라 디바이스에서 로컬 관리자 계정을 만들 수 있습니다.

*설정 > 계정 > Microsoft > 없는 사용자 > > 자격 증명을 사용할 수 없음*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>1단계: 디바이스가 Azure ID에 가입된지 확인
1.  사용자 전자 메일 및 암호로 로그인합니다.
2.  Go to 설정 > Accounts > Access Work or School. 
3.  에 연결된 사용자 **목록에서 사용자를 찾아야 합니다. 의 Azure AD.** 
4.  연결된 사용자가 있는 경우 2단계를 진행합니다. 그렇지 않은 경우 추가 작업이 필요하지 않습니다.
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>2단계: Azure AD에서 장치 연결 끊기
1.  연결된 **직장** 또는 학교 계정에서 연결 끊기를 탭합니다. 
2.  연결이 끊어진 것을 두 번 확인 합니다. 
3.  로컬 관리자 사용자 이름과 암호를 입력합니다. 디바이스의 연결이 끊어집니다.
4.  장치를 다시 시작합니다.
### <a name="step-3-join-the-device-to-azure-ad"></a>3단계: 디바이스를 Azure AD에 연결
1.  사용자가 로컬 관리자의 자격 증명으로 로그인합니다.
2.  다음으로 **설정** **계정으로** 이동한 다음 직장 **또는 학교에 액세스**
3.  탭 **커넥트**
4.  **중요:** **Azure AD에 가입을 탭합니다.**
5.  사용자의 전자 메일 주소와 암호를 입력합니다. 디바이스가 연결되어 있습니다.
6.  장치 다시 시작 
7.  전자 메일 주소 및 암호로 서명

## <a name="azure-ad-registered-company-owned"></a>Azure AD 등록(회사 소유)

장치 Windows 10 Azure AD가 등록되어 있는지 확인하려면 장치에서 다음 명령을 실행합니다.

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

디바이스가 Azure AD 등록된 경우 다음 출력이 표시됩니다.

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

장치에서 기존 Azure AD 등록 계정을 제거하려면

- 장치에서 Azure AD 등록 계정을 제거하려면 여기에서 다운로드할 수 있는 도구인 CleanupWPJ를 [CleanupWPJ.zip. ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)

- ZIP 파일을 추출하고 **WPJCleanup.cmd를 실행합니다.** 이 도구는 디바이스의 버전에 따라 올바른 실행 Windows 실행됩니다.

- 관리자는 그룹 정책과 같은 메커니즘을 사용하여 디바이스에 로그인한 사용자의 컨텍스트에서 디바이스에서 명령을 실행할 수 있습니다.

Azure AD에서 디바이스를 등록하라는 웹 계정 관리자 프롬프트를 사용하지 않도록 설정하려면 다음 레지스트리 값을 추가합니다. 

- 위치: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 형식: DWORD(32비트)
- 이름: BlockAADWorkplaceJoin
- 값 데이터: 1

이 레지스트리 값이 있는 경우 작업 공간 조인을 차단하고 사용자에게 디바이스에 가입하라는 메시지가 표시되지 않도록 해야 합니다.

## <a name="android"></a>Android

Android의 경우 사용자는 장치를 등록을 하지 않은 후 다시 등록해야 합니다. 이 완료는 앱 앱 또는 Microsoft Authenticator 앱을 통해 회사 포털 있습니다. 

- Microsoft Authenticator 앱에서 사용자는 장치 **등록으로 설정 > 수 있습니다.** 이 경우 사용자는 디바이스 등록을 등록을 다시 등록하고 다시 등록할 수 있습니다.
 
- 사용자가 회사 포털 탭으로 **이동하여** 디바이스를 제거할 수 있습니다. 그런 다음 디바이스를 사용하여 장치를 다시 회사 포털.
 
- 또한 사용자는 계정 설정 페이지에서 계정을 제거한 다음 직장 계정을 다시 추가하여 등록을 다시 등록 및 다시 등록할 수 있습니다.

앱 앱을 사용하여 Android에서 디바이스 등록을 등록을 Microsoft Authenticator:

1.  앱 Microsoft Authenticator 열고 으로 **설정.**
2.  장치 **등록 을 선택합니다.**
3.  등록을 다시 등록하지 않습니다.를 선택하여 디바이스 **등록을 등록을 하세요.**
4.  장치 **등록의** 경우 전자 메일 주소를 입력하여 장치를 다시 등록한 다음 등록을 **선택합니다.**

Android 장치 등록을 등록을 해지하고 Android 디바이스를 다시 등록하려면 설정:

1.  장치 **설정** 열고 계정으로 **이동하세요.**
2.  다시 등록할 직장 계정을 선택하고 계정 제거 **를 선택합니다.**
3.  계정이 제거된 후  계정 페이지에서 계정 추가 계정 > **선택합니다.**
4.  Workplace **Join의** 경우 전자 메일 주소를 입력하고 **가입을** 선택하여 장치 등록을 완료합니다.

Android에서 디바이스 등록을 해지하고 디바이스를 다시 등록하려면 다음을 회사 포털.

1.  시작 회사 포털 및 장치 **탭으로** 이동 합니다.
2.  장치를 선택하여 장치 세부 정보를 확인합니다.
3.  타원(세 점) 메뉴에서 장치 제거를 선택하고 대화 상자에서 확인하여 제거를 완료합니다. 
4.  이제 앱에 로그아웃해야 회사 포털 있습니다. 로그인을 **선택하여** 장치를 다시 등록합니다.

이 작업의 마이그레이션 단계 중에 필요한 작업 또는 관리 또는 사용에 미치는 영향에 대한 자세한 내용은 도이치랜드에서 마이그레이션을 위한 추가 Azure AD 정보의 Azure Active Directory(Azure AD)에 대한 정보를 [검토하세요.](ms-cloud-germany-transition-azure-ad.md)

## <a name="ios"></a>iOS

iOS 장치에서는 캐시된 계정을 장치에서 수동으로 제거하고, Microsoft Authenticator 등록을 해지하고, 장치의 모든 네이티브 앱에서 로그인해야 합니다.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>1단계: 있는 경우 앱의 Microsoft Authenticator 제거

1. 앱 앱의 계정을 Microsoft Authenticator 탭합니다.
2. 오른쪽 **설정** 아이콘을 탭합니다. if you don't see the **설정,** you might not using the latest version of Microsoft Authenticator.
3. 계정 **제거 단추를** 탭합니다.
4. 이 **디바이스의 모든 앱을 탭합니다.**
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>2단계: Microsoft Authenticator 앱에서 디바이스 등록을 Microsoft Authenticator

1. 오른쪽 위 모서리에서 메뉴 아이콘을 탭합니다.
2. 를 **설정** 다음 **장치 등록 을 탭합니다.**
4. 계정이 표시될 경우 **등록을** 하지 않은 장치 및 대화 상자에서 **계속을** 탭합니다. 그 이후에는 계정이 없습니다.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>3단계: 필요한 경우 개별 앱에서 서명

사용자는 앱, 앱 Outlook, Teams 및 OneDrive 앱으로 이동하고 해당 앱에서 계정을 제거할 수 있습니다.

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 마이그레이션 프로그램 정보](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)