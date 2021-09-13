---
title: 권장 보안 문서 정책 - Microsoft 365 보안 정책 | Microsoft Docs
description: SharePoint 파일 액세스를 보호하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: a031e60cbad91f71c55e678f03480b5d56c24efe
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213272"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>사이트 및 파일 보호를 SharePoint 정책 권장 사항

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- SharePoint Online 


이 문서에서는 권장 ID 및 장치 액세스 정책을 구현하여 사용자 및 장치 액세스 정책을 SharePoint 비즈니스용 OneDrive. 이 지침은 공통 ID 및 장치 액세스 [정책 을 빌드합니다.](identity-access-policies.md)

이러한 권장 사항은 요구의 세분성에 따라 적용할 수 있는 SharePoint 파일에 대한 세 가지 보안 및 보호 계층인 **기준,** 중요 및 높은 규제를 기반으로 **합니다.** 개요에서 이러한 권장 사항을 참조하여 이러한 보안 계층 및 권장되는 클라이언트 운영 체제에 대해 자세히 확인할 [수 있습니다.](microsoft-365-policies-configurations.md)

이 지침을 구현하는 것 외에도 중요하고 높은 규제 대상 콘텐츠에 SharePoint 적절한 사용 권한을 설정하는 등 적절한 양의 보호를 사용하여 SharePoint 사이트를 구성해야 합니다.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>공용 정책 업데이트 및 SharePoint 정책 비즈니스용 OneDrive

다음 다이어그램은 SharePoint 및 OneDrive 공용 ID 및 장치 액세스 정책에서 업데이트할 정책을 보여 주는 다이어그램입니다.

[![사용자 및 해당 종속 서비스에 대한 액세스를 보호하기 위한 Teams 업데이트 요약입니다.](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

공용 정책을 SharePoint 정책에 포함된 경우 새 정책만 만들어야 합니다. 조건부 액세스 정책의 경우 SharePoint 포함된 OneDrive.

새 정책은 사용자가 지정한 사이트에 특정 액세스 요구 사항을 적용하여 중요한 콘텐츠 및 높은 규제 대상 콘텐츠에 SharePoint 구현합니다.

다음 표에는 검토 및 업데이트하거나 새 정책을 만들어야 하는 정책이 SharePoint. 일반 정책은 일반 ID 및 장치 액세스 정책 문서의 관련 구성 [지침에 연결됩니다.](identity-access-policies.md)

|보호 수준|정책|추가 정보|
|---|---|---|
|**기준**|[로그인 위험이 중간 또는 높음인 경우 MFA *필요*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 SharePoint 할당에 다음을 포함합니다.|
||[최신 인증을 지원하지 않는 클라이언트 차단](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|클라우드 SharePoint 할당에 다음을 포함합니다.|
||[APP 데이터 보호 정책 적용](identity-access-policies.md#apply-app-data-protection-policies)|모든 권장 앱이 앱 목록에 포함해야 합니다. 각 플랫폼에 대한 정책을 업데이트해야 합니다(iOS, Android, Windows).|
||[호환 PC 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|클라우드 SharePoint 포함할 수 있습니다.|
||[앱에서 적용된 제한을 SharePoint](#use-app-enforced-restrictions-in-sharepoint)|이 새 정책을 추가합니다. 그러면 Azure Active Directory(Azure AD)에 지정된 설정을 사용하게 SharePoint. 이 정책은 모든 사용자에게 적용되지만 액세스 정책에 포함된 사이트에 SharePoint 영향을 미치게 됩니다.|
|**중요**|[로그인 위험이 낮거나 보통 또는 *높을* 때 MFA *필요*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 SharePoint 할당에 포함할 수 있습니다.|
||[호환 PC 및 *모바일* 장치 필요](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|클라우드 SharePoint 목록에 추가합니다.|
||SharePoint 액세스 제어 [정책:](#sharepoint-access-control-policies)관리되지 않는 장치에서 특정 SharePoint 사이트에 대한 브라우저 전용 액세스를 허용합니다.|이렇게 하면 파일을 편집하고 다운로드할 수 없습니다. PowerShell을 사용하여 사이트를 지정합니다.|
|**매우 엄격한 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 SharePoint 할당에 다음을 포함합니다.|
||[SharePoint 액세스 제어 정책:](#use-app-enforced-restrictions-in-sharepoint)관리되지 않는 장치에서 특정 SharePoint 사이트에 대한 액세스를 차단합니다.|PowerShell을 사용하여 사이트를 지정합니다.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>앱에서 적용된 제한을 SharePoint

SharePoint 액세스 제어를 구현하는 경우 Azure AD에서 이 조건부 액세스 정책을 만들어 Azure AD에 구성한 정책을 적용하도록 SharePoint. 이 정책은 모든 사용자에게 적용되지만 PowerShell을 사용하여 지정한 사이트에 대한 액세스에만 영향을 미치며 SharePoint.

해당 정책을 구성하는 경우 관리되지 않는 장치의 액세스 제어에서 "특정 SharePoint 사이트 모음 또는 OneDrive 계정에 대한 액세스 차단 또는 제한"을 [참조하세요.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>SharePoint 액세스 제어 정책

장치 액세스 제어를 사용하여 SharePoint 높은 규제 대상 콘텐츠를 사용하여 사이트 내 콘텐츠를 보호하는 것이 좋습니다. 이렇게 하는 경우 보호 수준을 지정하는 정책과 보호를 적용할 사이트를 만들 수 있습니다.

- 중요한 사이트: 브라우저 전용 액세스를 허용합니다. 이렇게 하면 사용자가 파일을 편집하고 다운로드할 수 없습니다.
- 높은 규제 대상 사이트: 관리되지 않는 장치에서 액세스를 차단합니다.

관리되지 않는 장치의 액세스 제어에서 "특정 SharePoint 사이트 모음 또는 OneDrive 액세스 차단 또는 제한"을 [참조하세요.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>이러한 정책이 함께 작동 하는 방법

사이트 사용 권한은 일반적으로 사이트 액세스에 SharePoint 기반한다는 점에 유의해야 합니다. 이러한 사용 권한은 사이트 소유자가 관리하며 매우 동적인 권한일 수 있습니다. 장치 SharePoint 정책을 사용하면 사용자가 기준, 중요 또는 높은 규제 대상 보호와 연결된 Azure AD 그룹에 할당되어 있는지 여부에 관계없이 이러한 사이트를 보호할 수 있습니다.

다음 그림에서는 장치 액세스 정책이 SharePoint 사이트에 대한 액세스를 보호하는 방법의 예를 제공합니다.

[![장치 액세스 SharePoint 보호하는 방법의 예](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[이 이미지의 더 큰 버전 참조](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James에는 기준 조건부 액세스 정책이 할당되어 있지만, 중요한 보호 또는 높은 규제가 적용된 SharePoint 사이트에 대한 액세스 권한을 부여할 수 있습니다.

- James가 중요하거나 높은 규제 대상 사이트에 액세스하는 경우 이 사용자가 PC를 사용하는 구성원인 경우 PC가 규정을 준수하는 한 액세스 권한이 부여됩니다.
- James가 중요한 사이트에 액세스하는 경우 기본 사용자에게 허용되는 관리되지 않는 전화 사용의 구성원인 경우 이 사이트에 대해 구성된 장치 액세스 정책으로 인해 중요한 사이트에 대한 브라우저 전용 액세스를 받게 됩니다.
- James가 높은 규제 대상 사이트에 액세스하는 경우 관리되지 않는 전화 사용의 구성원인 경우 이 사이트에 대해 구성된 액세스 정책으로 인해 차단됩니다. 관리되고 호환되는 PC를 사용하여 이 사이트에만 액세스할 수 있습니다.

## <a name="next-step"></a>다음 단계

![4단계: 클라우드 Microsoft 365 정책.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

조건부 액세스 정책 구성:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)