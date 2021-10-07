---
title: 최신 릴리스에 대한 광범위한 배포 예제
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: 최신 릴리스를 배포하는 조직에서 Windows 10과 Microsoft 365 앱용 채널을 사용하는 방법입니다.
ms.openlocfilehash: 6b0226a226742a89dc65ca0d32792db03c77e465
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193090"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>최신 릴리스에 대한 광범위한 배포 예제

이 채널 구성 예제는 비즈니스 우선순위에 맞게 최신 릴리스를 빠르게 배포하는 조직을 위한 예제입니다.

- Microsoft 앱과 서비스로 비즈니스 연속성을 보장합니다.
- Microsoft의 최신 기능과 픽스로 장치, 서비스 및 데이터 보안을 최대화합니다.
- Microsoft에서 제공하는 최신 기능을 사용하여 사용자 생산성을 최대화합니다.

이러한 목표는 광범위한 배포 이전에 기능적 유효성 검사를 위해 빠른 프로덕션 배포와 사용자와 장치의 대표 하위 집합을 통한 조기 심사 간의 균형을 찾는 IT 작업으로 이어집니다.

이 예제에서 조직은 유럽, 아프리카, 아시아 및 아메리카의 전 세계 건물에 5,000명의 직원을 두고 있습니다. 직원의 70%는 Microsoft 365 E3를 사용하고 나머지 조직은 Microsoft 365 E5를 사용합니다.

>[!Note]
>이 예제는 다양한 유형과 규모의 조직에 사용할 수 있는 배포 단계와 그룹을 사용하는 방법을 보여 주도록 설계되었습니다.
>

이 조직의 IT 인프라: 

- 대부분 Windows, Microsoft 365 앱 Microsoft 클라우드 서비스가 설치 기반의 60%로 동질적입니다.  IT 인프라를 단순화하고 간소화하기 위해 집중적으로 다년간 노력을 기울인 끝에 몇 가지 레거시 시스템이 남아 있습니다.
- 풍부한 경험이 있는 직원이 관리하고 Microsoft의 릴리스를 따라 사용자와 장치의 생산성과 보안을 유지하는 업무를 수행합니다.

## <a name="deployment-and-update-stages"></a>배포 및 업데이트 단계

이 예제에서 조직은 최신 릴리스의 빠른 배포 목표에 따라 2단계 배포 프로세스를 사용합니다.

1. **미리 보기 또는 파일럿 배포 사용:** 얼리어답터, IT 담당자, 대표 구성의 사용자 및 교육 담당자를 확인하고 반복합니다. 

   얼리어답터, IT 담당자, 대표 구성의 사용자는 새 기능이 조직의 나머지 부분에 배포되기 전에 다른 앱과 장치에서 기능의 유효성을 검사할 수 있습니다.

   변경 관리자는 광범위한 배포 전에 새로운 기능을 미리 살펴보고 메시징과 배포를 계획할 수 있습니다.

   교육 담당자는 광범위하게 배포하기 전에 새 내부 교육 과정을 계획하거나 새로운 기능에 대해 기존 교육 과정을 업데이트할 수 있습니다.

2. **프로덕션 배포:** 지역, 부서 또는 기타 배포 방법별로 나머지 모든 사용자에게 배포합니다.

## <a name="deployment-configuration-for-windows-10"></a>Windows 10용 배포 구성

전반적인 목표는 대표 사용자 그룹과 사용자의 장치 그룹에 의한 릴리스 미리 보기 채널 변경 사항의 유효성을 확인한 후 최신 반기 채널 릴리스를 광범위하게 배포하는 것입니다.

Windows 10 배포 방법 및 전략에 대한 자세한 내용은 [Windows 10 배포](/windows/deployment/)를 참조하세요.

| 단계 | 채널 | 배포 그룹 |
|:-------|:-------|:-----|
| 파일럿 |  **릴리스 미리 보기**  <ul><li>목적: 대표 장치와 구성(언어, 타사 앱)에 대한 유효성 검사를 위해 IT 담당자와 얼리어답터에게 기능 업데이트 배포 </li><li> 상태: 상업적 고객에게 완전히 호환되고 지원되며 귀하의 지원 계약에 불리하게 적용되지 않습니다. </li></ul> | **Win10ReleasePreviewChannel**(예제 이름) <br><br> 구성원은 다음을 포함하는 그룹입니다. <ul><li> 부서와 위치에 관계없는 Windows 마니아 </li><li> 유효성 검사가 필요한 구성이 있는 직원 </li><li> IT 관리자 및 IT 배포 담당자 </li><li> 변경 관리자 </li><li> 내부 교육 담당자 </li></ul> |
| 프로덕션 |  **반기 채널**  <ul><li>목적: 조직의 나머지 부분에 최신 기능 업데이트의 광범위한 배포 </li><li> 상태: 완전히 호환되고 지원됩니다. </li></ul> | **Win10SemiAnnualChannel**(예제 이름) <br><br> 구성원은 Win10ReleasePreviewChannel 그룹에 속하지 않은 모든 사용자입니다. |
||||

이 조직은 Windows Update 또는 Windows Server Update Services와 같은 반기 채널 릴리스를 배포할 때와 같은 방식으로 릴리스 미리 보기 채널 페이로드를 배포하는 모범 사례를 사용하며 두 채널 업데이트에 대해 동일한 정책을 적용합니다.

진행 중인 업데이트 프로세스:

1. 릴리스 미리 보기 채널 변경 내용이 Win10ReleasePreviewChannel(예제 이름) 배포 그룹에 배포됩니다.
2. Win10ReleasePreviewChannel 그룹 구성원은 릴리즈 미리 보기 채널 변경 내용이 작동함을 IT 배포 담당자에게 확인해 줍니다. 이들은 Microsoft에 피드백을 제공하고 추가 유효성 검사를 위해 다음 릴리스 미리 보기 채널 변경 내용을 기다릴 수 있습니다.
3. 반기 채널 기능 변경 내용이 Win10SemiAnnualChannel 배포 그룹에 배포됩니다. 

>[!Note]
>반기 채널을 사용하는 것이 좋지만, IT 부서는 관리 도구를 활용하여 조직 내에서 최신 반기 채널 릴리스를 배포할 시기를 결정한 다음 단계별로 배포해야 합니다.
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>Microsoft 365 앱에 대한 배포 구성

전반적인 목표는 대표 사용자 그룹과 사용자의 장치 그룹에 의한 현재 채널(미리 보기) 변경 사항의 유효성을 확인한 후 현재 채널(미리 보기) 릴리스를 광범위하게 배포하는 것입니다.

Microsoft 365 앱 배포 방법 및 전략에 대한 자세한 내용은 [Microsoft 365 앱 배포](/deployoffice/plan-office-365-proplus)를 참조하세요.

| 단계 | 채널 | 배포 그룹 |
|:-------|:-------|:-----|
| 파일럿 |  **현재 채널(미리 보기)** <ul><li> 목적: {대표 사용자 그룹에 새로운 Microsoft 365 앱 기능 살짝 살펴보기 제공} 현재 기능(미리 보기) 사용자를 대상으로 테스트하고 프로덕션 준비가 완료되는 즉시 기능 업데이트 배포 </li><li> 상태: 완전히 호환되고 지원됩니다.</li><li> 빈도: 매월 2~3번 업데이트합니다. </li></ul> | **AppsCurrentChannelPreview**(예제 이름) <br><br> 구성원은 다음을 포함하는 그룹입니다. <ul><li> 부서와 위치에 관계없는 Office 앱 마니아 </li><li> 유효성 검사가 필요한 구성이 있는 직원 </li><li> IT 관리자 및 IT 배포 담당자 </li><li> 변경 관리자 </li><li> 내부 교육 담당자 </li></ul>|
| 프로덕션 | **현재 채널** <ul><li> 목적: 조직의 나머지 부분에 최신 기능 업데이트의 광범위한 배포 </li><li> 상태: 완전히 호환되고 지원됩니다. </li></ul> |  **AppsCurrentChannel**(예제 이름) <br><br> 구성원은 AppsCurrentChannelPreview 그룹에 속하지 않은 모든 사용자입니다. |
|||

진행 중인 업데이트 프로세스:

1. 현재 채널(미리 보기) 변경 내용이 AppsCurrentChannelPreview 배포 그룹에 배포됩니다.
2. AppsCurrentChannelPreview 그룹 구성원은 현재 채널(미리 보기) 변경 내용이 작동함을 IT 배포 담당자에게 확인해 줍니다. 이들은 Microsoft에 피드백을 제공하고 추가 유효성 검사를 위해 다음 릴리스 미리 보기 채널 변경 내용을 기다릴 수 있습니다.
3. 현재 채널 변경 내용이 AppsCurrentChannel 배포 그룹에 배포됩니다. 

## <a name="visual-summary"></a>시각적 요약

다음은 이 예제 조직에서 사용하는 제품, 해당 채널 및 배포 그룹입니다. 

![최신 릴리스의 광범위한 배포를 위한 배포 그룹](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>참고 항목

[배포 및 업데이트 채널 예제 구성](deploy-update-channels-examples.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)