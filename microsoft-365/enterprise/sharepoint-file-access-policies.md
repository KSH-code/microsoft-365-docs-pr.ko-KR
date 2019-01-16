---
title: 권장되는 보안 문서 정책 - Microsoft 365 Enterprise | Microsoft Docs
description: SharePoint 파일 액세스를 보호하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72dd50649dba9e290d50c2831557c06db3cb7586
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870004"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint 사이트 및 파일을 보호 하기 위한 정책 권장 사항
이 문서에서는 권장된 id 및 SharePoint Online 및 비즈니스용 OneDrive를 보호 하는 장치 액세스 정책을 구현 하는 방법에 설명 합니다. 이 설명서는의 [일반적인 id 및 정책에 액세스 하는 장치를](identity-access-policies.md)기반으로 수행 합니다. 

이러한 권장 사항을 기반 보안의 서로 다른 세 계층으로 적용할 수 있는 SharePoint 파일에 대 한 보호 요구의 세분성에 따라 및: **초기 계획**, **중요 한**및 **규제 된 매우**합니다. 이러한 보안 계층 및 이러한 권장 사항 [개요](microsoft-365-policies-configurations.md)에 의해 참조 되는 권장된 클라이언트 운영 체제에 대 한 자세한 수 있습니다.

이 지침을 구현 하는 것 외에도 오른쪽 양의/소문자를 구분 하 고 매우 규제 된 콘텐츠에 대 한 적절 한 사용 권한 설정을 비롯 한 보호를 사용 하 여 SharePoint 사이트를 구성 해야 합니다. 초기 계획, 소문자를 구분 하 고 매우 규제 된 보호에 대 한 사이트를 만드는 방법에 대 한 자세한 내용은 [SharePoint Online 보안 사이트 및 파일을](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)참조 하십시오. 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>SharePoint 및 비즈니스용 OneDrive를 포함 하는 일반적인 정책을 업데이트 합니다.
다음 다이어그램에서는 비즈니스를 위한 SharePoint Online 및 OneDrive에서 파일을 보호 하는 것에 대 한 권장된 정책 집합을 보여줍니다. 어떤 정책이 업데이트 하거나 SharePoint Online 및 비즈니스용 OneDrive에 대 한 보호를 추가 하려면 새로 만든 해야를 나타냅니다.

![SharePoint Online 및 OneDrive에 대 한 정책 요약](../images/identity-access-ruleset-sharepoint.png)

일반적인 정책을 만들 때 SharePoint Online 포함, 한 경우 새 정책을 만들 필요 합니다. 조건부 액세스 규칙을 구성, SharePoint Online 비즈니스용 OneDrive 포함 합니다.

새 정책을 지정 하는 SharePoint 사이트에 특정 액세스 요구 사항을 적용 하 여 중요 한 및 높은 규제 된 콘텐츠에 대 한 장치 보호를 구현 합니다. 

다음 표에서 검토 및 업데이트 또는 SharePoint Online에 대 한 새로 만들기를 내보내도록 정책을 보여줍니다. 일반적인 정책 [일반적인 id 및 장치 액세스 정책](identity-access-policies.md) 문서에 연결 된 구성 지침에 대 한 링크입니다.


|보호 수준|Policies(정책)|추가 정보|
|:---------------|:-------|:----------------|
|**기준**|[로그인 위험 *보통* 또는 *높음* 때 MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 앱의 배정에서 SharePoint Online 포함|
|        |[현대 인증을 지원 하지 않는 블록 클라이언트](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|클라우드 앱의 배정에서 SharePoint Online 포함|
|        |[응용 프로그램 보호 정책 정의](identity-access-policies.md#define-app-protection-policies)|모든 권장된 앱 앱 목록에 포함 되었는지 확인 해야 합니다. 각 플랫폼 (iOS, Android, Windows)에 대 한 정책을 업데이트 해야 합니다.|
|        |[호환 Pc 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|SharePoint Online 클라우드 앱 목록에 포함|
|        |[SharePoint Online에 적용 하는 응용 프로그램 제한 사용](#use-app-enforced-restrictions-in-sharepoint-online)|이 새 정책을 추가 합니다. SharePoint Online에서 지정한 설정을 사용 하 여 Azure AD 인지를 나타냅니다. 이 규칙 적용 하는 모든 사용자에 게 있지만 SharePoint Online 액세스 정책에 포함 된 사이트에 대 한 액세스에만 적용|
|**중요**|[로그인 위험 *낮음*, *보통* , *높음* 때 MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|SharePoint Online 클라우드 앱의 할당에 포함|
|         |[준수 Pc *및* 모바일 장치 필요](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|SharePoint Online 클라우드 앱 목록에 포함|
||[SharePoint Online 액세스 제어 정책](#sharepoint-online-access-control-policies): 특정 SharePoint 사이트에 비관리 장치에서 브라우저 전용 액세스를 허용|이렇게 하면 편집 하 고 파일을 다운로드할 수 없습니다. PowerShell을 사용 하 여 사이트를 지정 하려면|
|**높은 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 앱의 배정에서 SharePoint Online 포함|
||[SharePoint Online 액세스 제어 정책](#use-app-enforced-restrictions-in-sharepoint-online): 비관리 장치에서 특정 SharePoint 사이트에 대 한 액세스를 차단|PowerShell을 사용 하 여 사이트를 지정 하려면|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>SharePoint Online에서 app 적용 제한 사용
SharePoint Online에 대 한 액세스 제어를 구현 하는 경우 SharePoint Online에서 구성할 정책 준수를 위해 Azure AD를 구별 하 Azure AD에이 조건부 액세스 정책을 만들어야 합니다. 이 규칙 적용 하는 모든 사용자에 게 하지만 SharePoint Online의 액세스 제어를 만들 때 PowerShell을 사용 하 여 지정 된 사이트에 대 한 액세스를 영향을 줍니다.

이 문서에서이 정책을 참조 "차단 또는 제한 액세스를 특정 SharePoint 사이트 모음 또는 OneDrive 계정에"를 구성 하려면: [비관리 장치에서 액세스를 제어](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)합니다.


## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online 액세스 제어 정책
장치 액세스 제어를 사용 하 여 중요 한 및 높은 규제 된 콘텐츠를 사용 하 여 SharePoint 사이트에서 콘텐츠를 보호 하는 것이 좋습니다. 보호 하 고 보호를 적용할 사이트의 수준을 지정 하는 정책을 만들어이 작업을 수행 합니다. 
- 중요 한 사이트: 브라우저 전용 액세스를 허용 합니다. 이 사용자가 편집 하 고 파일을 다운로드할 수 없습니다.
- 매우 사이트 규제 된: 비관리 장치에서 액세스를 차단 합니다.

이 문서의 "특정 SharePoint 사이트 모음 또는 OneDrive 계정에 액세스 제한 또는 차단"을 참조: [비관리 장치에서 액세스를 제어](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) 합니다. 

## <a name="how-these-policies-work-together"></a>이러한 정책이 함께 작동 하는 방법
것은 그 SharePoint 사이트 사용 권한을 사이트에 대 한 액세스를 위한 비즈니스 요구에 따라 일반적으로 이해 하는 것이 중요 합니다. 이러한 사용 권한은 사이트 소유자가 관리 하 고 매우 동적 될 수 있습니다. 장치 액세스 정책을 통해 사용자는 Azure AD 그룹에 할당 된 여부에 관계 없이 이러한 사이트를 보호 하는 SharePoint를 사용 하 여 매우 보호 규제 된 또는 연관 된 초기 계획, 소문자를 구분 합니다. 

다음 그림에서는 SharePoint 장치 액세스 정책은 사이트에 대 한 액세스를 보호 하는 방법의 예를 제공 합니다.

![장치 액세스 정책 SharePoint 사이트를 보호 하는 방법](../images/SharePoint-rules-scenario.png)

이 그림의 내용
- James 초기 보호와 관련 된 조건부 액세스 정책에 할당 된 하지만 그 수 있는 액세스 권한이 부여 중요 한 내용 또는 매우 규제 된 보호와 관련 된 SharePoint 사이트에 있습니다. 
- James가 자신의 PC를 사용 하 여의 멤버가 중요 한 내용 또는 매우 규제 된 사이트에 액세스 하는 경우 액세스 자신의 PC 규격이으로 부여 됩니다.
- James 구성원의 초기 사용자에 대 한 허용 하는 관리 되지않는 전화를 사용 하는 중요 한 사이트에 액세스 하는 경우가이 사이트에 대해 구성 된 장치 액세스 정책으로 인해 중요 한 사이트에 대 한 브라우저 전용 액세스를 받습니다. 
- James가 비관리가 전화를 사용 하 여의 구성원 인 매우 규제 사이트에 액세스 하는 경우가이 사이트에 대해 구성 된 액세스 정책으로 인해 차단 됩니다. 만 관리 하 고 규정을 준수 PC를 사용 하 여이 사이트에 액세스할 수 있는 그 합니다.


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>다음 단계
[SharePoint Online 사이트 및 파일 보호](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
