---
title: 데이터 개인 정보 보호 규정에 대한 정보 보호를 Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 데이터 보호, Microsoft 365 전자 메일을 포함하여 GDPR 및 캘리포니아 소비자 개인 정보 보호법(CCPA)과 같은 데이터 개인 정보 보호 규정에 Microsoft Teams SharePoint 구성합니다.
ms.openlocfilehash: 7517faa02ea74d5a9934e22595d61a34e99067a5
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756590"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>데이터 개인 정보 보호 규정에 대한 정보 보호를 Microsoft 365

조직은 사용자가 IT 인프라에 저장된 개인 정보(사내 및 클라우드 모두 포함)를 보호, 관리 및 제어해야 하는 지역별 데이터 개인 정보 보호 규정이 적용될 수 있습니다. 데이터 개인 정보 보호 규정의 가장 좋은 예는 유럽 연합의 GDPR(일반 데이터 보호 규정)입니다. 데이터 개인 정보 보호 규정을 준수하지 못하면 상당한 벌금이 부과될 수 있습니다.

Microsoft 365 유형의 예로는 Microsoft Teams, Exchange 전자 메일 및 SharePoint 파일의 OneDrive. 이 솔루션은 위험 평가 방법 및 개인 데이터를 보호하기 위한 적절한 조치를 취하는 방법에 대한 지침을 Microsoft 365. 여기에는 데이터 개인 정보 보호 인시던트 보호, 관리 및 대응할 수 있는 개인 정보 식별이 포함됩니다.

![데이터 개인 정보 보호 규정에 대한 정보 보호입니다.](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

데이터 개인 정보 요구에 대한 Microsoft 365, 장치 및 위협 방지 컨트롤을 사용하는 경우 추가 정보가 제공됩니다.

이 비디오를 시청하고 배포 프로세스에 대한 개요를 확인하세요.
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

이러한 Microsoft 365 및 기능은 정보 보호 기준을 충족하는 데 도움이 됩니다.

| 기능 또는 특징 | 설명 | 라이선싱 |
|:-------|:-----|:-------|
| 규정 관리자 | 규정 준수 활동을 관리하고 현재 규정 준수 구성의 전체 점수를 얻은 다음 개선을 위한 권장 사항을 찾아야 합니다. 이 도구는 워크플로 기반 위험 평가 도구로 Microsoft 365 규정 준수 센터. | Microsoft 365 E3 및 E5 |
| Office 365용 Microsoft Defender | 전자 메일 메시지, 사무실 문서 및 협업 도구와 같은 Microsoft 365 앱과 데이터를 공격으로부터 보호합니다. | Microsoft 365 E3 및 E5 |
| 민감도 레이블 | 사용자의 생산성과 공동 작업 능력을 방해하지 않고 조직의 데이터를 분류하고 보호합니다. 전자 메일, 파일 또는 사이트에 다양한 수준의 보호가 있는 레이블을 지정합니다. | Microsoft 365 E3 및 E5 |
| 데이터 손실 방지(DLP). | 개인 정보를 포함하는 데이터의 위험하거나 부적절하거나 부적절한 공유를 내부 및 외부적으로 감지, 경고 및 차단합니다. | Microsoft 365 E3 및 E5 |
| 데이터 보존 레이블 및 정책. | 정보 거버넌스 제어를 구현합니다. 여기에는 조직의 정책 또는 데이터 규정을 준수하기 위해 데이터(예: 고객과 관련된 개인 데이터)를 유지할 기간 결정이 포함됩니다. | Microsoft 365 E3 및 E5 |
| 전자 메일 암호화 | 조직 내부 및 외부의 사용자 간에 암호화된 전자 메일 메시지를 보내고 받아 개인 데이터를 보호합니다. | Microsoft 365 E3 및 E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>이 솔루션의 지침 구성

하나 이상의 개인 정보 관련 규정을 충족하는 데 도움이 되는 Microsoft 365 도구를 이해하기 위해 이 지침은 섹션으로 구성됩니다.

![데이터 개인 정보 보호 규정에 대한 정보 보호를 구현하는 단계입니다.](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

이러한 각 섹션은 이 솔루션의 별도 문서에 해당합니다.

> [!NOTE]
> 데이터 개인 정보 보호 의무에 이미 익숙하고 기존 계획에 대해 실행하고 있는 경우 금지, 보호, 보존 및 조사 지침에 집중할 수 있습니다.

> [!IMPORTANT]
> 이 지침에 따라 반드시 데이터 개인 정보 보호 규정을 준수할 필요는 없습니다. 특히 기능의 컨텍스트 외부에 있는 단계 수를 고려합니다. 귀하는 규정 준수를 보장하고 법률 및 규정 준수 팀에 문의하거나 규정 준수를 전문적으로 하는 타사의 지침과 조언을 구할 책임이 있습니다.

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>계획: 데이터 개인 정보 보호 위험을 평가하고 중요한 항목 식별

조직이 적용해야 하는 데이터 개인 정보 규정 및 위험을 평가하는 것은 조직에서 기능 구성을 포함하여 개선을 구현하기 전에 먼저 Microsoft 365. 이 작업으로는 조직에서 준수해야 하는 규정 제어가 적용된 특정 중요한 정보 유형에 대한 전반적인 준비 평가 또는 식별이 포함됩니다.

자세한 내용은 데이터 개인 정보 보호 위험 평가 및 [중요한 항목 식별을 참조하세요.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>추적: 위험 평가 실행 및 준수 점수 확인

Microsoft 365 규정 준수 센터 있는 준수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank"></a>관리자는 사용자에게 적용되는 여러 데이터 개인 정보 규정과 관련된 것뿐만 아니라 개선 작업을 전반적으로 추적하고 관리할 수 있는 기본 제공 기능을 제공합니다.

각 규정과 관련된 기본 제공 평가 템플릿을 사용할 수 있습니다. 여기서 선택한 각 평가 템플릿에 대한 작업 항목을 추적하고 특정 규제 컨트롤을 보고 특정 작업과 관련될 수 있습니다.

자세한 내용은 준수 [관리자를 사용하여 개선 작업 관리를 참조하세요.](information-protection-deploy-compliance.md)

## <a name="prevent-protect-personal-data"></a>방지: 개인 데이터 보호

Microsoft 365 데이터 개인 정보 규정 준수를 준수하는 데 사용할 수 있는 ID, 장치 및 위협 방지 기능을 제공합니다.

자세한 내용은 데이터 개인 정보 규정에 ID, 장치 [및 위협 방지 사용을 참조하세요.](information-protection-deploy-identity-device-threat.md)

이 문서에서는 이러한 영역에서 일반적으로 데이터 개인 정보 보호 규정이 요구하는 사항에 대해 간략하게 설명하고 구현 요구 사항을 충족하는 데 도움이 되는 추가 정보로 연결되는 Microsoft 365 솔루션 목록을 제공합니다.

## <a name="protect-information-subject-to-data-privacy-regulation"></a>데이터 개인 정보 보호 규정을 준수하는 정보 보호

데이터 개인 정보 보호 규정은 GDPR, 캘리포니아 소비자 보호법(CCPA), HIPAA-HITECH(미국 의료 개인 정보 보호법) 및 브라질 데이터 보호법(LGPD)의 샘플 집합에 있는 네 가지 데이터 개인 정보 보호 규정에 대한 정보 보호를 위한 40개 이상의 제어를 포함하여 사용자 환경에서 사용할 수 있는 다양한 개인 정보 보호 컨트롤을 규정합니다.

자세한 내용은 조직에서 데이터 개인 [정보 보호 규정을 준수하는 정보 보호를 참조하세요.](information-protection-deploy-protect-information.md)

이 문서에서는 조직의 데이터 개인 정보 보호에 대한 정보 보호 요구 사항을 해결하기 위해 사용할 수 있는 기본 제어 체계에 대해 개설합니다.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>보존: 데이터 개인 정보 보호 규정이 적용된 정보 관리

데이터 개인 정보 규정은 GDPR, CCPA, HIPAA-HITECH 및 LGPD 샘플 집합의 네 가지 데이터 개인 정보 보호 규정에 대한 24개 이상의 제어를 포함하여 사용자 환경에서 사용할 수 있는 개인 정보 거버넌스 제어를 요구합니다.

자세한 내용은 조직에서 데이터 개인 [정보 보호 규정이 적용된 정보 거버넌스를 참조하세요.](information-protection-deploy-govern.md)

데이터 개인 정보 보호 규정은 의도적인 보존, 삭제 및 보관과 같은 정보 거버넌스와 관련하여 모호할 수 있는 반면, 이 문서에서는 조직의 데이터 개인 정보 보호에 대한 주소 정보 거버넌스 요구 사항을 사용할 수 있는 기본 제어 체계를 &mdash; &mdash; 제공합니다.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>조사: 데이터 개인 정보 보호 인시던트 모니터링, 조사 및 대응

관련 Microsoft 365 작동 시 조직의 데이터 개인 정보 인시던트 모니터링, 조사 및 대응에 도움이 되는 다양한 기능을 사용할 수 있습니다.

이러한 기능을 사용하는 프로세스, 절차 및 기타 설명서는 규제 기관의 규정 준수를 입증하는 데 중요할 수 있습니다.

자세한 내용은 조직의 데이터 개인 정보 인시던트 모니터링 및 [대응을 참조하세요.](information-protection-deploy-monitor-respond.md)

## <a name="training-for-administrators"></a>관리자 교육

Microsoft Learn의 이러한 교육 모듈은 정보 보호에 중요한 기능을 알아보는 데 도움이 될 수 있습니다.


#### <a name="information-protection"></a>정보 보호

|교육:|Microsoft 365를 사용하여 엔터프라이즈 정보 보호|
|:---|:---|
|![Teams 보호 교육 아이콘입니다.](../media/protect-enterprise-information-microsoft-365.svg)|조직의 정보를 보호하고 보안을 유지하는 것이 어느 때보다 어려워졌습니다. Microsoft 365로 엔터프라이즈 정보 보호 학습 경로는 우발적인 과도한 공유 또는 오용으로부터 중요한 정보를 보호하는 방법, 데이터를 검색하고 분류하는 방법, 민감도 레이블을 사용하여 중요한 정보를 보호하는 방법 및 중요한 정보가 손실되지 않도록 보호하기 위해 모니터링하고 분석하는 방법에 대해 설명합니다. 이 학습 경로를 통해 인증된 Microsoft 365: 보안 관리자 연결 및 인증: Microsoft 365 인증: 관리 전문가 인증을 Enterprise 수 있습니다.<br><br>1 hr - Learning 경로 - 5개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>ID 및 액세스

|교육:|Azure Active Directory로 ID 및 엑세스 권한 보호|
|:---|:---|
|![ID 및 액세스 교육 아이콘.](../media/protect-identity-and-access-with-microsoft-365.svg)|ID 및 Access 학습 경로에는 최신 ID 및 액세스 기술, 인증 강화 도구 및 조직 내 ID 보호에 대한 지침이 포함되어 있습니다. Microsoft의 액세스 및 ID 기술을 사용하면 온-프레미스 또는 클라우드에 있는 조직의 ID를 보호할 수 있으며, 사용자가 어느 위치에서나 안전하게 작업하도록 할 수 있습니다. 이 학습 경로를 통해 Microsoft 365 인증: 보안 관리자 학위 및 Microsoft 365 인증: 엔터프라이즈 관리 전문가 인증서를 준비할 수 있습니다.<br><br>2시간 52분 - Learning 경로 - 6개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/modules/m365-identity-overview/introduction/)