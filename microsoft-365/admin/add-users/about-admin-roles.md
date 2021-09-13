---
title: Microsoft 365 관리 센터의 관리자 역할 정보
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: 서비스 관리자와 같은 관리자 역할은 비즈니스 기능에 매핑되며 관리 센터에서 특정 작업을 수행할 수 있는 권한을 부여합니다.
ms.openlocfilehash: 42c28d230cef36f7f6e0421cc46f64a53222eca8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185363"
---
# <a name="about-admin-roles"></a>관리자 역할 정보

Microsoft 365 또는 Office 365 구독은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>를 사용해 조직의 사용자에게 할당할 수 있는 관리자 역할 집합과 함께 제공됩니다. 각 관리자 역할은 일반적인 비즈니스 기능에 해당하며, 조직의 구성원에게 관리 센터에서 특정 작업을 수행할 수 있는 권한을 부여합니다.

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>를 통해 Azure AD 역할과 Microsoft Intune 역할을 관리할 수 있습니다. 그러나 해당 역할은 Azure AD 포털과 Intune 관리 센터에서 사용할 수 있는 역할의 하위 집합입니다.

## <a name="before-you-begin"></a>시작하기 전에

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 관리할 수 있는 자세한 Azure AD 역할 설명의 전체 목록을 찾고 계신가요? Azure Active Directory의 관리자 역할 권한을 확인하세요. [Azure AD 기본 제공 역할](/azure/active-directory/roles/permissions-reference).

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 관리할 수 있는 자세한 Intune 역할 설명의 전체 목록을 찾고 계신가요?  [Microsoft Intune으로 RBAC(역할 기반 액세스 제어)](/mem/intune/fundamentals/role-based-access-control)를 확인하세요.

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 역할을 할당하는 방법에 대한 자세한 내용은 [관리자 역할 할당](assign-admin-roles.md)을 참조하세요.

## <a name="watch-what-is-an-admin"></a>시청: 관리자란 무언인가요?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>역할 지정에 대한 보안 지침

관리자는 중요한 데이터 및 파일에 액세스할 수 있으므로 조직의 데이터를 보다 안전하게 유지하기 위해서 이 지침을 따르는 것이 좋습니다.

| 권장 사항                  | 중요한 이유는 무엇입니까?                 |
| :------------------- | :------------------- |
| 2 ~ 4 전역 관리자 보유  | 다른 전역 관리자만 전역 관리자 비밀번호를 재설정할 수 있으므로 계정 잠금시 조직에 전역 관리자가 2명 이상 있는 것이 좋습니다. 그러나 전역 관리자는 조직의 설정 및 대부분의 데이터에 거의 무제한으로 액세스할 수 있어 보안 위협에 해당하므로 전역 관리자는 4명을 초과하지 않을 것을 권장합니다. |
| *최소 허용* 역할 할당    | *최소 허용* 역할을 지정하는 것은 관리자가 작업을 수행하는 데 필요한 액세스 권한만 부여하는 것을 의미합니다. 예를 들어, 누군가 직원 암호를 재설정하게 하려는 경우 무제한 전역 관리자 역할을 할당하지 말고 비밀번호 관리자 또는 헬프 데스크 관리자와 같은 제한된 관리자 역할을 할당해야 합니다. 이를 통해 데이터를 안전하게 유지할 수 있습니다.                 |
| 관리자에게 다단계 인증 요구                  |    모든 사용자에게 MFA를 요구하는 것이 사실 좋은 생각이며 관리자는 반드시 MFA를 사용하여 로그인해야 합니다. MFA는 사용자가 자신이 누구인지 확인하기 위해 두 번째 식별 방법을 입력하도록 합니다. 관리자는 많은 고객 및 직원 데이터에 액세스할 수 있으며 MFA가 필요한 경우 관리자 암호가 손상되더라도 두 번째 식별 양식없이 암호를 사용할 수 없습니다.  <br><br>다음에 사용자가 로그인할 때 MFA를 켜면 계정 복구를 위해 대체 이메일 주소와 전화 번호를 제공해야 합니다.  <br> [다단계 인증 설정](../security-and-compliance/set-up-multi-factor-authentication.md)          |

설정이나 페이지를 편집할 권한이 없다는 메시지가 관리 센터에 표시된다면 이는 해당 권한이 없는 역할이 할당되었기 때문입니다.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>일반적으로 사용되는 Microsoft 365 관리 센터 역할

Microsoft 365 관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**역할 할당**</a>으로 이동한 다음 아무 역할이나 선택하여 세부 정보 창을 열 수 있습니다. **사용 권한** 탭을 선택하여 해당 역할에 할당된 관리자가 수행할 수 있는 작업에 대한 자세한 목록을 볼 수 있습니다. 역할에 사용자를 추가하려면 **할당된** 또는 **할당된 관리자** 탭을 선택합니다.

조직에서 다음 역할을 할당하기만 하면 됩니다. 기본적으로 Microsoft에서는 대부분의 조직에서 사용하는 역할을 먼저 보여줍니다. 역할을 찾을 수 없는 경우 목록 맨 아래로 이동하여 **모든 범주 보기** 를 선택하세요. (역할과 연결된 cmdlet을 비롯한 자세한 내용은 [Azure AD 기본 제공 역할](/azure/active-directory/roles/permissions-reference)을 참조하세요.)

|관리자 역할     |이 역할에는 누가 할당되어야 하나요?  |
|---------|---------|
|청구 관리자     |   구매를 진행하고 구독 및 서비스 요청을 관리하고 서비스 상태를 모니터링을 하는 사용자에게 청구 관리자 역할을 할당합니다. <br><br> 청구 관리자는 다음 기능을 수행할 수 있습니다.<br> - 청구의 모든 측면 관리 <br> - Azure Portal에서 지원 티켓 만들기 및 관리 <br>  |
|Exchange 관리자     |   사용자의 전자 메일 사서함, Microsoft 365 그룹 및 Exchange Online을 확인하고 관리 해야 하는 사용자에게 Exchange 관리자 역할을 할당합니다. <br><br> Exchange 관리자는 다음 작업도 수행할 수 있습니다.<br> - 사용자의 사서함에서 삭제된 항목 복구 <br> - "다른 사람 이름으로 보내기" 및 "대신 보내기" 대리인 설정 <br>  |
|전역 관리자     |   Microsoft 온라인 서비스를 통해 대부분의 관리 기능과 데이터에 대한 전역 액세스 권한을 필요로 하는 사용자에게 전역 관리자 역할을 할당합니다. <br><br> 사용자에게 너무 많은 전역 액세스 권한을 부여 하는 것은 보안상 위험하며 2~4명의 전역 관리자를 사용하는 것이 좋습니다. <br><br> 다음 작업은 전역 관리자만 수행할 수 있습니다.<br> - 관리자 암호 다시 설정 <br> - 도메인 추가 및 관리 <br> <br> **참고**: Microsoft 온라인 서비스에 등록하는 사람은 자동으로 전역 관리자가 됩니다. |
|전역 읽기 권한자    |   관리자 센터에서 전역 관리자가 볼 수 있는 관리자 기능 및 설정을 보아야 하는 사용자에게 전역 읽기 권한자 역할을 할당합니다. 전역 리더 관리자는 설정을 편집할 수 없습니다.   |
|그룹 관리자     |   Microsoft 365 관리 센터 및 Azure Active Directory 포털을 포함하여 관리 센터 전체에서 모든 그룹 설정을 관리해야 하는 사용자에게 그룹 관리자 역할을 할당합니다. <br><br> 그룹 관리자는 다음을 수행할 수 있습니다.<br> - Microsoft 365 그룹 만들기, 편집, 삭제 및 복원 <br> - 그룹 생성, 만료 및 명명 정책 만들기 및 업데이트 <br> - Azure Active Directory 보안 그룹 만들기, 편집, 삭제 및 복원| 
|헬프데스크 관리자     |   다음 작업을 수행해야 하는 사용자에게 헬프데스크 관리자 역할을 할당합니다.<br> - 암호 초기화 <br> - 강제로 사용자에게 로그 아웃 <br> - 서비스 요청 관리 <br> - 서비스 상태 모니터링 <br> <br> **참고**: 헬프 데스크 관리자는 관리자 이외의 사용자와 디렉터리 읽기 권한자, 게스트 초대자, 헬프 데스크 관리자, 메시지 센터 읽기 권한자 및 보고서 읽기 권한자와 같은 역할을 할당 받은 사용자만 도울 수 있습니다.      |
|라이선스 관리자    |   사용자 라이선스를 할당 및 제거하고 사용 위치를 편집해야 하는 사용자에게 라이선스 관리자 역할을 할당합니다. <br/><br/> 라이선스 관리자도 다음 기능을 수행할 수 있습니다. <br> - 그룹 기반 라이선스에 대한 라이선스 할당 다시 처리 <br> - 그룹 기반 라이선스를 위해 그룹에 제품 라이선스 할당  |
|Office 앱 관리자    |   다음 작업을 수행해야 하는 사용자에게 Office 앱 관리자 역할을 할당합니다. <br> - Office 클라우드 정책 서비스를 사용하여 Office에 대한 클라우드 기반 정책을 만들고 관리 <br> - 서비스 요청 만들기 및 관리 <br> - Office 앱에서 사용자에게 표시되는 새로운 콘텐츠를 관리   <br> - 서비스 상태 모니터링  |
|암호 관리자  |   비 관리자 및 암호 관리자의 암호를 재설정해야 하는 사용자에게 암호 관리자 역할을 할당합니다.   |
|메시지 센터 읽기 권한자 |   다음을 수행해야 하는 사용자에게 메시지 센터 읽기 권한자 역할을 할당합니다. <br> - 메시지 센터 알림 모니터링 <br> - 메시지 센터 게시물 및 업데이트의 주간 전자 메일 다이제스트 가져오기 <br> - 메시지 센터 게시물 공유 <br> - 사용자 및 그룹과 같은 Azure AD 서비스에 대한 읽기 전용 액세스 권한 보유|
|파워 플랫폼 관리자 |   다음을 수행해야 하는 사용자에게 Power Platform 관리자 역할을 할당합니다. <br> - Power Apps, Power Automate 및 데이터 손실 방지를 위한 모든 관리 기능 관리 <br> - 서비스 요청 만들기 및 관리 <br> - 서비스 상태 모니터링  |
|보고서 읽기 권한자 |   다음 작업을 수행해야 하는 사용자에게 보고서 읽기 권한자 역할을 할당합니다. <br> - Microsoft 365 관리 센터의 사용량 현황 데이터 및 활동 보고서 보기 <br> - Power BI 채택 콘텐츠 팩에 대한 액세스 권한 얻기 <br> - Azure AD의 로그인 보고서 및 활동에 대한 액세스 권한 얻기 <br> - Microsoft Graph 보고 API에서 반환된 데이터 보기|
|서비스 지원 관리자   |   서비스 지원 관리자 역할을 관리자나 사용자에게 추가 역할로 할당하려면 일반적인 관리자 역할 외에 다음 작업을 수행해야 합니다. <br> - 서비스 요청 열기 및 관리 <br> - 메시지 센터 게시물 보기 및 공유 <br> - 서비스 상태 모니터링   |
|SharePoint 관리자    |   Sharepoint Online 관리 센터에 액세스하고 관리해야 하는 사용자에게 SharePoint 관리자 역할을 할당합니다. <br><br>SharePoint 관리자는 다음 작업도 수행할 수 있습니다. <br> - 사이트 만들기 및 삭제 <br> - 사이트 모음 및 전역 SharePoint 설정 관리   |
|Teams 서비스 관리자    |   Teams 관리 센터에 액세스하고 관리해야 하는 사용자에게 Teams 서비스 관리자 역할을 할당합니다. <br><br>Teams 서비스 관리자도 다음을 수행할 수 있습니다. <br> - 모임 관리 <br> - 회의 브리지 관리 <br> - 페더레이션, 팀 업그레이드 및 팀 클라이언트 설정을 포함한 모든 조직 전체 설정 관리   |
|사용자 관리자     |    모든 사용자를 위해 다음 작업을 수행해야 하는 사용자에게 사용자 관리자 역할을 할당합니다. <br> - 사용자 및 그룹 추가 <br> - 라이선스 할당 <br> - 대부분의 사용자 속성 관리 <br> - 사용자 보기 만들기 및 관리 <br> - 암호 만료 정책 설정 <br> - 서비스 요청 관리 <br> - 서비스 상태 모니터링 <br><br>  사용자 관리자는 또한 관리자가 아닌 사용자와 디렉터리 읽기 권한자, 게스트 초대자, 헬프 데스크 관리자, 메시지 센터 읽기 권한자, 보고서 읽기 권한자 역할이 할당된 사용자에 대해 다음 작업을 수행할 수 있습니다.  <br> - 사용자 이름 관리<br> - 사용자 삭제 및 복원<br> - 암호 초기화 <br> - 강제로 사용자에게 로그 아웃 <br> - 업데이트(FIDO) 장치 키   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 파트너를 위한 위임 된 관리

Microsoft 파트너와 함께 업무를 진행하는 경우에는 파트너에게 관리자 역할을 할당할 수 있습니다. 파트너 또한 사용자 회사 또는 파트너 회사의 사용자들에게 관리자 역할을 할당할 수 있습니다. 예를 들어 파트너가 대신 사용자의 온라인 조직을 설정하고 관리하는 경우 이 기능이 필요할 수 있습니다.
  
파트너는 다음과 같은 역할을 할당할 수 있습니다. 
  
- **관리자 에이전트** 파트너 센터를 통해 다단계 인증을 관리하는 것을 제외하고는 전역 관리자와 동등한 권한입니다.

- **헬프데스크 에이전트** 헬프데스크 관리자와 동일한 권한입니다.

파트너가 이러한 역할을 사용자에게 할당하기 전에 파트너를 사용자 계정에 위임된 관리자로 추가해야 합니다. 이 프로세스는 공인 파트너가 시작 합니다. 파트너는 사용자가 파트너에게 위임된 관리자 역할을 수행할 권한을 부여할 것인지 묻는 전자 메일을 보냅니다. 안내 사항은 [파트너 관계 승인 또는 제거](../misc/add-partner.md)를 참조하십시오.
  
## <a name="related-content"></a>관련 콘텐츠

[관리자 역할 할당](assign-admin-roles.md)(문서)\
[Microsoft 365 관리 센터의 Azure Active Directory 역할](azure-ad-roles-in-the-mac.md)(문서)\
[Microsoft 365 관리 센터의 활동 보고](../activity-reports/activity-reports.md)(문서)\
[Exchange Online 관리자 역할](about-exchange-online-admin-role.md)(문서)
