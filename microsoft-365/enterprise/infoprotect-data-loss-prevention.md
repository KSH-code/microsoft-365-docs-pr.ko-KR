---
title: '5단계: Office 365 데이터 손실 방지 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365의 Office 365 데이터 손실 방지를 이해 및 배포
ms.openlocfilehash: d0a8beae3797e59eb1eb130afb9fd123be57d909
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308357"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>5단계: Office 365 데이터 손실 방지 구성

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Office 365 보안 및 준수 센터의 DLP(데이터 손실 방지) 정책을 사용하면 Microsoft 365 전체에서 중요한 정보를 식별하고, 모니터링하고, 자동으로 보호할 수 있습니다. DLP 정책을 사용하여 다음을 수행할 수 있습니다.

- Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams와 같은 다양한 위치에서 중요한 정보를 식별합니다.
- 문서에 대한 액세스를 차단하거나 문서를 포함하는 전자 메일을 차단하여 중요한 정보를 실수로 공유하지 않도록 합니다.
- 데스크톱 버전의 Excel, PowerPoint 및 Word에서 중요한 정보를 모니터링하고 보호합니다.
- 사용자가 워크플로를 중단하지 않고 전자 메일 알림 및 정책 팁을 사용하여 규정 준수 상태를 유지하는 방법을 알 수 있도록 도와줄 수 있습니다. 
- 조직의 DLP 정책과 일치하는 내용을 표시하는 DLP 보고서를 확인합니다.

DLP 정책을 지정합니다.

- **위치:** Microsoft Teams 채팅 및 채널뿐 아니라, Exchange Online, SharePoint Online 및 비즈니스용 OneDrive 사이트와 같은 위치.
- **시기:** 특정 정책 규칙 내에서 일치해야 하는 조건.
- **방법:** 일치하는 정책 규칙의 조치를 일치하는 조건에 자동으로 적용합니다.

위의 명령이 반환하는 결과는 다음과 같습니다.

- 이 위치(위치)에 있는 문서의 경우, 콘텐츠가 규칙의 조건과 일치하면(시기) 해당 규칙에 지정된 조치를 자동으로 적용합니다(방법).

필요한 DLP 정책의 집합을 확인하려면 문서와 데이터 손실 방지가 필요한 문서 내 데이터 유형을 분석해야 합니다. 예를 들어, 미국 내 금융 조직인 경우, 사회 보장 번호가 있는 문서가 조직 외부에서 공유되거나 전자 메일로 조직 외부의 위치로 전송되는 것을 방지하는 DLP 정책을 작성합니다.

다음으로, 정확한 DLP 동작을 보장하고 가양성을 최소화하기 위해 테스트 위치를 사용하여 정책을 구성하고 테스트합니다.

마지막으로, 새 정책과 기대하는 동작을 직원에게 알리고 위치의 범위를 확장하여 조직에 이를 공개합니다.

자세한 내용은 [DLP 정책 권장 사항 시작하기](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)를 참조하세요.

중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step5)을 확인하세요.

## <a name="next-step"></a>다음 단계


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[Office 365에 대한 권한 있는 액세스 관리 구성](infoprotect-configure-privileged-access-management.md)|


