---
title: '2단계: ID'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise에 대한 ID 인프라를 배포하는 단계입니다.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870124"
---
# <a name="phase-2-identity"></a>2단계: ID

![](./media/deploy-foundation-infrastructure/identity_icon.png)

Microsoft 365 Enterprise에서 적절히 계획되고 실행되는 ID 인프라는 인증된 사용자와 장치에서만 생산성 작업 및 데이터에 액세스할 수 있도록 하고 보안을 강화할 수 있는 방법을 제공합니다.

>[!Note]
>ID 인프라를 이미 배포한 경우 [ID 종료 조건](identity-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Microsoft 365 Enterprise ID 인프라 계획 및 배포 

다음 단계를 사용하여 클라우드에서 새 ID 인프라를 계획 및 배포할 수 있습니다. 또한 이러한 단계를 사용하여 Microsoft 365 Enterprise와 함께 작동하도록 기존 온-프레미스 또는 하이브리드 ID 인프라를 조정할 수 있습니다. 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [사용자 및 그룹 계획](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [전역 관리자 계정 보호](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [주문형 전역 관리자 설정](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [암호 재설정 간소화](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [다단계 인증 설정](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [자격 증명 손상으로부터 보호](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [디렉터리 동기화](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [동기화 상태 모니터링](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [암호 업데이트 간소화](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [사용자 로그인 간소화](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [Office 365 로그인 페이지 사용자 지정](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [자동 라이선싱 설정](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [테넌트 및 로그인 활동 모니터링](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [사용자가 자신의 그룹을 만들고 관리하도록 허용](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [동적 그룹 구성원 설정](identity-automatic-group-membership.md) |

이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](identity-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.

## <a name="identity-and-device-access-recommendations"></a>ID 및 장치 액세스 권장 사항

Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. ID을 확인하려면 다음 문서의 권장 사항 및 설정과 함께 이 작업 단계의 다음 단계를 사용하세요.

- [필수 구성 요소](identity-access-prerequisites.md)
- [일반 ID 및 장치 액세스 정책](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

다음 리소스에서는 Microsoft의 IT 전문가가 Microsoft 365 Enterprise의 ID 기능을 계획하고 배포한 방식을 알아봅니다.

- [Microsoft에서 사용자 ID 및 보안 액세스 관리](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [상승된 액세스 권한에 대해 Azure AD Privileged Identity Management 사용](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso의 Microsoft 365 Enterprise 사용 방식

가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스를 위해 [Microsoft 용 하이브리드 ID 인프라를 구축](contoso-identity.md)한 방식을 알아봅니다.

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [사용자 및 그룹 계획](identity-plan-users-groups.md) |
