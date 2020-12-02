---
title: Microsoft Cloud 독일의 마이그레이션에 대 한 추가 장치 정보
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
description: '요약: Microsoft cloud 전라남도 (Microsoft 클라우드 독일)에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 이동할 때의 추가 장치 정보입니다.'
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551956"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud 독일의 마이그레이션에 대 한 추가 장치 정보

## <a name="frequently-asked-questions"></a>자주하는 질문

**조직이 영향을 받는지 어떻게 확인할 수 있나요?**

관리자는 등록 된 장치가 있는지 확인 해야 합니다 `https://portal.microsoftazure.de` . 조직에서 장치를 등록 한 경우 영향을 받습니다.

**사용자에 게 미치는 영향은 무엇입니까?**

등록 된 장치의 사용자는 마이그레이션이 [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 마이그레이션 단계로 들어간 후 더 이상 로그인 할 수 없습니다.  

조직이 Microsoft 클라우드 독일의 연결을 끊기 전에 모든 장치가 전 세계 끝점에 등록 되어 있는지 확인 합니다.
  
**사용자가 자신의 장치를 다시 등록 해야 하는 경우**

[Microsoft Cloud 독일](ms-cloud-germany-transition.md#how-is-the-migration-organized) 마이그레이션 단계가 진행 되는 동안에만 장치를 등록 취소 하 고 다시 등록 해야 합니다.

**마이그레이션 후 장치 상태를 복원 하려면 어떻게 해야 하나요?**

Azure AD에 등록 된 하이브리드 Azure AD-조인 및 회사 소유 Windows 장치의 경우 관리자는 이전 장치 상태의 등록을 취소 하는 원격으로 트리거된 워크플로를 통해 이러한 장치 마이그레이션을 관리할 수 있습니다.
  
Azure AD에 등록 되어 있는 개인 Windows 장치를 비롯 한 다른 모든 장치에서는 최종 사용자가 다음 단계를 수동으로 수행 해야 합니다. Azure AD-결합 된 장치의 경우 사용자의 등록을 취소 하 고 다시 등록 하려면 로컬 관리자 계정이 있어야 합니다.

Microsoft는 장치 상태를 성공적으로 복원 하는 방법에 대 한 지침을 게시 합니다. 
 
**모든 내 장치가 공용 클라우드에 등록 되어 있는지 어떻게 알 수 있나요?**

장치가 공용 클라우드에 등록 되어 있는지 여부를 확인 하려면 Azure AD 포털에서 Excel 스프레드시트로 장치 목록을 내보내고 다운로드 해야 합니다. 그런 다음 [Microsoft 클라우드 독일](ms-cloud-germany-transition.md#how-is-the-migration-organized) 마이그레이션 단계와는 별개의 _registeredTime_ 열을 사용 하 여 등록 된 장치를 필터링 합니다.

장치 등록은 테 넌 트가 마이그레이션 후 비활성화 되며 사용 하거나 사용 하지 않도록 설정할 수 없습니다. Intune을 사용 하지 않는 경우 구독에 로그인 하 고이 명령을 실행 하 여 옵션을 다시 활성화 합니다.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows 하이브리드 Azure AD 조인

### <a name="windows-down-level"></a>Windows 하위 수준

_Windows 하위 수준 장치_ 는 현재 이전 버전의 windows를 실행 하는 windows 장치 (예: windows 8.1 또는 windows 7) 이거나 windows Server 버전을 2019 및 2016 보다 이전의 상태로 실행 하는 것입니다. 이러한 장치를 이전에 등록 한 경우 해당 장치를 등록 취소 하 고 다시 등록 해야 합니다. 

이전에 Windows 하위 수준 장치가 Azure AD에 연결 되었는지 여부를 확인 하려면 장치에서 다음 명령을 사용 합니다.

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

장치가 이전에 Azure AD에 가입 된 경우 및 장치에 글로벌 Azure AD 끝점에 대 한 네트워크 연결이 있으면 다음 출력이 표시 됩니다.

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

영향을 받는 장치에는 "장치 상태" 값이 "알 수 없음"으로 나타납니다. 출력이 "장치 가입 되지 않음" 또는 "장치 상태" 값이 "정상" 인 경우 다음 지침을 무시 합니다.

장치가 가입 되어 있고 (deviceId, 손도장 등) 해당 "장치 상태" 값이 "알 수 없음" 인 것을 표시 하는 장치에 대해서만 관리자가 해당 하위 수준 장치에 로그인 한 도메인 사용자 로그인 컨텍스트에서 다음 명령을 실행 해야 합니다.

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

이전 명령은 Windows 하위 수준 장치에서 도메인 사용자 로그인 당 한 번만 실행 하면 됩니다. 이 명령은 도메인 사용자 로그인의 컨텍스트에서 실행 해야 합니다. 

사용자가 다음에 로그인 할 때이 명령을 실행 하지 않으려면 충분히 주의 해야 합니다. 위의 명령이 실행 되 면 로그인 한 사용자에 대해 로컬 하이브리드 Azure AD에 연결 된 컴퓨터의 참가 상태를 지웁니다. 또한 컴퓨터가 테 넌 트에 연결 된 하이브리드 Azure AD로 계속 구성 되어 있으면 사용자가 다시 로그인 할 때 가입을 시도 합니다.

### <a name="windows-current"></a>Windows 현재

#### <a name="unjoin"></a>않도록

이전에 Windows 10 장치가 Azure AD에 연결 되었는지 확인 하려면 장치에서 다음 명령을 실행 합니다.

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

장치가 하이브리드 Azure AD에 연결 된 경우 관리자는 다음과 같은 출력을 볼 수 있습니다.

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

출력이 "AzureAdJoined: No" 이면 다음 지침을 무시 합니다.

장치가 Azure AD에 가입 되어 있음을 보여주는 장치에만 다음 명령을 관리자 권한으로 실행 하 여 장치에 대 한 가입 상태를 제거 합니다.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

위의 명령은 Windows 장치에서 관리 컨텍스트에서 한 번만 실행 하면 됩니다.

#### <a name="hybrid-ad-joinre-registration"></a>하이브리드 AD Join\Re-Registration

장치가 글로벌 Azure AD 끝점에 대 한 네트워크 연결을 사용 하는 경우 사용자 또는 관리자 간섭 없이 디바이스가 자동으로 Azure AD에 연결 됩니다. 


## <a name="windows-azure-ad-join"></a>Windows Azure AD 조인

### <a name="unjoin"></a>않도록

이전에 Windows 10 장치를 Azure AD에 조인한 적이 있는지 확인 하려면 사용자 또는 관리자가 장치에서 다음 명령을 실행할 수 있습니다.

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

디바이스가 Azure AD에 가입 되어 있으면 사용자 또는 관리자에 게 다음과 같은 출력이 표시 됩니다.

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

출력이 "AzureAdJoined: NO" 이면 다음 지침을 무시 합니다.

사용자: 디바이스가 Azure AD에 가입 된 경우 사용자는 설정에서 디바이스의 가입을 제거할 수 있습니다. 장치를 Azure AD에서 unjoining 전에 해당 장치에 로컬 관리자 계정이 있는지 확인 합니다. 장치에 다시 로그인 하려면 로컬 관리자 계정이 필요 합니다.

관리자: 조직의 관리자가 가입 된 사용자의 장치를 그룹 정책 등의 메커니즘을 사용 하 여 연결 하는 방법으로 해당 디바이스를 구독 하지 않을 수 있습니다. 관리자가 Azure AD에서 장치를 unjoining 전에 장치에 로컬 관리자 계정이 있는지 확인 해야 합니다. 장치에 다시 로그인 하려면 로컬 관리자 계정이 필요 합니다.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

위의 명령은 Windows 장치에서 관리 컨텍스트에서 한 번만 실행 하면 됩니다. 

### <a name="azure-ad-joinre-registration"></a>Azure AD Join/재등록

사용자는 Windows 설정에서 Azure AD에 연결할 수 있음: **설정 > 계정 > 액세스 하 여 회사 또는 학교 > 연결** 합니다.
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD 등록 (회사 소유)

Windows 10 장치가 등록 되어 있는지 여부를 확인 하려면 장치에서 다음 명령을 실행 합니다.

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

디바이스가 Azure AD에 등록 되어 있으면 다음과 같은 출력이 표시 됩니다.

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

장치에서 기존 Azure AD 등록 계정을 제거 하려면:

- 장치에서 Azure AD-등록 된 계정을 제거 하려면 [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)에서 다운로드할 수 있는 도구인 CleanupWPJ를 사용 합니다.

- ZIP 파일을 추출 하 고 **WPJCleanup를 실행 합니다.** 이 도구는 장치의 Windows 버전에 따라 올바른 실행 파일을 시작 합니다.

- 관리자는 그룹 정책 같은 메커니즘을 사용 하 여 장치에서 로그인 한 모든 사용자의 컨텍스트에서이 명령을 장치에서 실행할 수 있습니다.

Azure AD에 장치를 등록 하도록 웹 계정 관리자 프롬프트를 사용 하지 않도록 설정 하려면 다음 레지스트리 값을 추가 합니다. 

- 위치: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 유형: DWORD (32 비트)
- 이름: BlockAADWorkplaceJoin
- 값 데이터: 1

이 레지스트리 값이 있으면 작업 영역 조인이 차단 되 고 사용자가 장치에 연결 하 라는 메시지가 표시 되지 않습니다.

## <a name="android"></a>Android

Android의 경우 사용자는 해당 디바이스의 등록을 취소 하 고 다시 등록 해야 합니다. Microsoft Authenticator 앱 또는 회사 포털 앱을 통해이 작업을 수행할 수 있습니다. 

- 사용자는 Microsoft 인증자 앱에서 **설정 > 장치 등록** 으로 이동할 수 있습니다. 사용자가 자신의 장치를 등록 취소 하 고 다시 등록할 수 있습니다.
 
- 회사 포털에서 사용자가 **장치** 탭으로 이동 하 여 장치를 제거할 수 있습니다. 그런 다음 회사 포털을 사용 하 여 장치를 다시 등록 합니다.
 
- 또한 사용자는 계정 설정 페이지에서 계정을 제거한 다음 다시 추가 하는 방법으로 작업을 등록 취소 하 고 재등록 할 수 있습니다.

Microsoft Authenticator 앱을 사용 하 여 Android에서 장치를 등록 취소 하 고 다시 등록 하려면:

1.  Microsoft Authenticator 앱을 열고 **설정** 으로 이동 합니다.
2.  **장치 등록** 을 선택 합니다.
3.  **등록 취소** 를 선택 하 여 장치를 등록 취소 합니다.
4.  **장치 등록** 의 경우 전자 메일 주소를 입력 하 여 장치를 다시 등록 한 다음 **레지스터** 를 선택 합니다.

Android 설정 페이지를 사용 하 여 Android 장치를 등록 취소 하 고 다시 등록 하려면:

1.  **장치 설정을** 열고 **계정** 으로 이동 합니다.
2.  다시 등록할 작업 계정을 선택 하 고 **계정 제거** 를 선택 합니다.
3.  계정을 제거한 후 계정 페이지에서 **계정 > 작업 계정 추가** 를 **선택 합니다.**
4.  **회사 조인의** 경우 사용자의 전자 메일 주소를 입력 하 고 **참가** 를 선택 하 여 장치 등록을 완료 합니다.

회사 포털에서 Android의 장치 등록을 취소 하 고 다시 등록 하려면:

1.  회사 포털을 시작 하 고 **장치** 탭으로 이동 합니다.
2.  장치를 선택 하 여 장치 세부 정보를 확인 합니다.
3.  줄임표 (점 3 개) 메뉴에서 **장치 제거** 를 선택 하 고 대화 상자에서 확인 하 여 제거를 완료 합니다.
4.  이제 회사 포털 앱에서 로그 아웃 해야 합니다. **로그인** 을 선택 하 여 장치를 다시 등록 합니다.

이 작업의 마이그레이션 단계 중에 필요한 작업 또는 관리 또는 사용 현황에 대 한 영향에 대 한 자세한 내용은 [Microsoft Cloud 독일의 마이그레이션에 대 한 추가 일반 정보](ms-cloud-germany-transition-add-general.md#azure-active-directory)에서 Azure Active Directory에 대 한 정보를 참조 하십시오.

## <a name="ios"></a>iOS

IOS 장치에서는 사용자가 Microsoft 인증자에서 캐시 된 계정을 수동으로 제거 하 고, 장치를 등록 취소 하 고, 장치의 기본 앱에서 로그 아웃 해야 합니다.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>1 단계: (있는 경우) Microsoft Authenticator 앱에서 계정을 제거 합니다.

1. Microsoft Authenticator 앱에서 계정을 누릅니다.
2. 오른쪽 위 모서리에 있는 **설정** 아이콘을 누릅니다. **설정** 아이콘이 표시 되지 않으면 최신 버전의 Microsoft 인증자를 사용 하지 않을 수 있습니다.
3. **계정 제거** 단추를 누릅니다.
4. **이 장치의 모든 앱을** 탭 합니다.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>2 단계: Microsoft Authenticator 앱에서 장치 등록 취소

1. 오른쪽 위 모서리에 있는 메뉴 아이콘을 누릅니다.
2. **설정** 및 **장치 등록** 을 차례로 누릅니다.
4. 계정이 표시 되 면 **장치 등록 해제** 를 탭 하 고 대화 상자에서 **계속** 합니다. 그 후에 계정이 표시 되지 않습니다.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>3 단계: 필요한 경우 개별 앱에서 로그 아웃

사용자는 Outlook, 팀 및 OneDrive와 같은 개별 앱으로 이동 하 여 해당 앱에서 계정을 제거할 수 있습니다.

## <a name="more-information"></a>추가 정보

시작 하기:

- [Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동 하는 경우:

- [마이그레이션 단계 작업 및 영향](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
