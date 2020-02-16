---
title: 권장되는 보안 문서 정책 - Microsoft 365 Enterprise | Microsoft Docs
description: SharePoint 파일 액세스를 보호하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: d11b2682b9699e61a4c9ecfa47eb73de87de5e4f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084212"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint 사이트 및 파일을 보호 하기 위한 정책 권장 사항

이 문서에서는 SharePoint Online 및 비즈니스용 OneDrive를 보호 하기 위해 권장 되는 id 및 장치 액세스 정책을 구현 하는 방법을 설명 합니다. 이 지침은 [일반 id 및 장치 액세스 정책을](identity-access-policies.md)기반으로 합니다.

이러한 권장 사항은 **기본**, **중요**및 **높은 규제**의 요구 사항에 따라 적용할 수 있는 SharePoint 파일에 대 한 세 가지 보안 및 보호 계층을 기반으로 합니다. 이러한 보안 계층 및 권장 되는 클라이언트 운영 체제에 대 한 자세한 내용은 [개요](microsoft-365-policies-configurations.md)의 이러한 권장 사항을 참조 하세요.

이 지침을 구현 하는 것 외에도 중요 한 콘텐츠와 고도로 규제 된 콘텐츠에 대 한 적절 한 사용 권한을 설정 하는 것을 포함 하 여 SharePoint 사이트를 올바른 보호 수준으로 구성 해야 합니다. 기준, 중요 및 고도로 규제 된 보호를 위한 사이트를 만드는 방법에 대 한 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)를 참조 하세요.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>SharePoint 및 비즈니스용 OneDrive를 포함 하도록 일반 정책 업데이트

다음 다이어그램에서는 SharePoint Online 및 비즈니스용 OneDrive에서 파일을 보호 하기 위한 권장 정책 집합을 보여 줍니다. SharePoint Online 및 비즈니스용 OneDrive에 대 한 보호를 추가 하기 위해 업데이트 하거나 새로 만들어야 하는 정책을 나타냅니다.

![SharePoint Online 및 OneDrive에 대 한 정책 요약](../media/identity-access-ruleset-sharepoint.png)

공용 정책을 만들 때 SharePoint Online을 포함 한 경우에는 새 정책만 만들면 됩니다. 조건부 액세스 규칙을 구성 하는 경우 SharePoint Online에 비즈니스용 OneDrive가 포함 됩니다.

새 정책은 지정 하는 SharePoint 사이트에 특정 액세스 요구 사항을 적용 하 여 중요 한 콘텐츠 및 고도로 규제 된 콘텐츠에 대 한 장치 보호를 구현 합니다.

다음 표에는 SharePoint Online을 검토 하 고 업데이트 하거나 새를 만드는 데 필요한 정책이 나와 있습니다. 공통 정책- [일반 id 및 장치 액세스 정책](identity-access-policies.md) 문서의 관련 구성 지침에 대 한 링크를 제공 합니다.

|보호 수준|정책도|추가 정보|
|:---------------|:-------|:----------------|
|**기준선**|[로그인 위험이 *보통* 또는 *높을* 때 MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 앱 할당에 SharePoint Online 포함|
|        |[최신 인증을 지원하지 않는 클라이언트 차단](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|클라우드 앱 할당에 SharePoint Online 포함|
|        |[앱 보호 정책 정의](identity-access-policies.md#define-app-protection-policies)|모든 권장 앱이 앱 목록에 포함 되어 있는지 확인해 보십시오. 각 플랫폼의 정책 (iOS, Android, Windows)을 업데이트 해야 합니다.|
|        |[호환 PC 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|클라우드 앱 목록에 SharePoint Online 포함|
|        |[SharePoint Online에서 앱 적용 제한 사용](#use-app-enforced-restrictions-in-sharepoint-online)|새 정책을 추가 합니다. 이렇게 하면 Azure AD에서 SharePoint Online에 지정 된 설정을 사용 하 게 됩니다. 이 규칙은 모든 사용자에 게 적용 되지만 SharePoint Online access 정책에 포함 된 사이트에 대 한 액세스에만 영향을 줍니다.|
|**중요**|[로그인 위험이 *낮은* *경우 MFA* 필요 **](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 앱의 할당에 SharePoint Online 포함|
|         |[준수 Pc *및* 모바일 장치 요구](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|클라우드 앱 목록에 SharePoint Online 포함|
||[SharePoint Online 액세스 제어 정책](#sharepoint-online-access-control-policies): 관리 되지 않는 장치에서 특정 SharePoint 사이트에 대 한 브라우저 전용 액세스 허용|이렇게 하면 파일을 편집 하 고 다운로드할 수 없습니다. PowerShell을 사용 하 여 사이트 지정|
|**높은 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 앱 할당에 SharePoint Online 포함|
||[SharePoint Online 액세스 제어 정책](#use-app-enforced-restrictions-in-sharepoint-online): 관리 되지 않는 장치에서 특정 SharePoint 사이트에 대 한 액세스 차단|PowerShell을 사용 하 여 사이트 지정|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>SharePoint Online에서 앱 적용 제한 사용

SharePoint Online에서 액세스 제어를 구현 하는 경우 azure ad에서이 조건부 액세스 정책을 만들어 SharePoint Online에서 구성한 정책을 적용 해야 합니다. 이 규칙은 모든 사용자에 게 적용 되지만 SharePoint Online에서 액세스 제어를 만들 때 PowerShell을 사용 하 여 지정한 사이트에 대 한 액세스에만 영향을 줍니다.

이 정책을 구성 하려면이 문서의 "특정 SharePoint 사이트 모음 또는 OneDrive 계정에 대 한 액세스 차단 또는 제한" ( [관리 되지 않는 장치에서의 액세스 제어](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622))을 참조 하세요.

## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online 액세스 제어 정책

Microsoft는 장치 액세스 제어를 통해 중요 하 고 규제 된 콘텐츠를 사용 하 여 SharePoint 사이트의 콘텐츠를 보호 하는 것이 좋습니다. 이 작업을 수행 하려면 보호를 적용할 사이트 및 보호 수준을 지정 하는 정책을 만듭니다.

- 중요 한 사이트: 브라우저 전용 액세스 허용 이렇게 하면 사용자가 파일을 편집 하 고 다운로드할 수 없습니다.
- 높은 규제 대상 사이트: 관리 되지 않는 장치에서 액세스를 차단 합니다.

이 문서의 "특정 SharePoint 사이트 모음 또는 OneDrive 계정에 대 한 액세스 차단 또는 제한" ( [관리 되지 않는 장치에서의 액세스 제어](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622))을 참조 하세요.

## <a name="how-these-policies-work-together"></a>이러한 정책이 함께 작동 하는 방식

SharePoint 사이트 사용 권한은 일반적으로 사이트에 대 한 액세스에 대 한 비즈니스 요구 사항을 기반으로 한다는 점을 이해 하는 것이 중요 합니다. 이러한 사용 권한은 사이트 소유자가 관리 하며 고도로 동적인 권한 일 수 있습니다. SharePoint 장치 액세스 정책을 사용 하면 사용자가 기준, 중요 또는 고도로 규제 된 보호와 관련 된 Azure AD 그룹에 할당 되었는지 여부에 관계 없이 이러한 사이트에 대 한 보호를 보장할 수 있습니다.

다음 그림에서는 SharePoint 장치 액세스 정책이 사이트에 대 한 액세스를 보호 하는 방법의 예를 보여 줍니다.

![SharePoint 장치 액세스 정책에서 사이트를 보호 하는 방법](../media/SharePoint-rules-scenario.png)

이 그림의 내용

- James는 기준 보호와 관련 된 조건부 액세스 정책에 할당 되지만 중요 하거나 고도로 규제 된 보호에 연결 되어 있는 SharePoint 사이트에 대 한 액세스 권한을 부여 받을 수 있습니다.
- James가 PC를 사용 하는 구성원 인 중요 한 사이트에 액세스 하는 경우 해당 PC가 준수 하는 한 액세스 권한이 부여 됩니다.
- James가 중요 한 사이트에 액세스 하는 경우, 기본 사용자에 게 허용 되는 관리 되지 않는 휴대폰을 사용 하는 구성원 인 경우이 사이트에 대해 구성 된 장치 액세스 정책으로 인해 중요 한 사이트에 대 한 브라우저 전용 액세스 권한이 부여 됩니다.
- James가 관리 되지 않는 휴대폰을 사용 하는 구성원 인 고도로 규제 된 사이트에 액세스 하는 경우이 사이트에 대해 구성 된 액세스 정책으로 인해 차단 됩니다. 관리 및 준수 PC를 사용 해야만이 사이트에 액세스할 수 있습니다.

## <a name="next-steps"></a>다음 단계

[SharePoint Online 사이트 및 파일 보호](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
