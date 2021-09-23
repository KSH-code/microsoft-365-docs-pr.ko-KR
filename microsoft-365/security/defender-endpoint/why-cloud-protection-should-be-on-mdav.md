---
title: 클라우드 보호를 사용하도록 설정해야 하는 Microsoft Defender 바이러스 백신
description: 클라우드 보호를 설정해야 하는 이유를 Microsoft Defender 바이러스 백신. 끝점 작업을 위한 Microsoft Defender의 많은 보안 기능에 도움이 됩니다.
keywords: Microsoft Defender 바이러스 백신, 클라우드 보호, 보안 기능, 샘플 제출
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 09/21/2021
ms.collection: m365-security-compliance
ms.openlocfilehash: 11b45edc944cb60c476a79dc921bd211e04514ef
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491448"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>클라우드 보호를 사용하도록 설정해야 하는 Microsoft Defender 바이러스 백신

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 바이러스 백신

Microsoft Defender 바이러스 백신 클라우드 보호는 끝점 및 네트워크 전체에서 맬웨어를 방지하는 데 도움이 됩니다. 끝점용 Microsoft Defender의 특정 보안 기능은 클라우드 보호가 활성화되어 있는 경우만 작동하기 때문에 클라우드 보호를 설정하는 것이 좋습니다. 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="클라우드 보호에 종속된 기능을 보여주는 다이어그램":::](enable-cloud-protection-microsoft-defender-antivirus.md)

다음 표에는 클라우드 보호에 종속된 기능이 요약되어 있습니다. <br/><br/>

| 기능/기능  | 구독 |  설명  |
|---------|---------|--------|
| 클라우드의 메타데이터 확인  | Microsoft 365 E5 또는 E3 | Microsoft Defender 바이러스 백신 클라우드 서비스는 추가 방어 계층으로 기계 학습 모델을 사용 합니다. 이러한 기계 학습 모델에는 메타데이터가 포함되어 있으므로 의심스러우거나 악의적인 파일이 감지되면 해당 메타데이터가 검사됩니다. <br/><br/>자세한 내용은 [Blog: Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection를 참조하세요.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)  |
| 클라우드 보호 및 샘플 제출 | Microsoft 365 E5 또는 E3 | 파일 및 실행 파일은 검색 및 분석을 위해 Microsoft Defender 바이러스 백신 클라우드 서비스로 보낼 수 있습니다. <br/><br/>자세한 내용은 에서 클라우드 보호 및 샘플 [제출을 Microsoft Defender 바이러스 백신.](cloud-protection-microsoft-antivirus-sample-submission.md)<br/><br/>**참고:** 자동 샘플 제출은 클라우드 보호를 사용하나 독립 실행형 설정으로 구성할 수도 있습니다.         |
| 변조 방지 | Microsoft 365 E5 | 변조 보호는 조직의 보안 설정에 대한 원치 않는 변경으로부터 보호하는 데 도움이 됩니다. Microsoft 365 Defender 포털에서 변조 보호를 적용하려면 클라우드 보호를 사용하도록 설정해야 합니다. <br/><br/>자세한 내용은 [변조 방지로 보안 설정 보호를 참조하세요.](prevent-changes-to-security-settings-with-tamper-protection.md)        |
| 처음에 차단 | Microsoft 365 E5 또는 E3 | 바로 차단은 새로운 맬웨어를 감지하고 몇 초 이내에 차단합니다. 의심스러우거나 악의적인 파일이 감지되면, 무단 차단 기능은 클라우드 보호 백드를 쿼리하고 파일에 대한 추론, 기계 학습 및 자동화된 분석을 적용하여 위협인지 여부를 판단합니다.<br/><br/>자세한 내용은 ["최초 차단"이란?을 참조하세요.](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)   |
| 긴급 서명 업데이트 | Microsoft 365 E5 | 악성 콘텐츠가 감지되면 긴급 서명 업데이트 및 수정 내용이 배포됩니다. 다음 정기 업데이트를 기다리지 않고 몇 분 이내에 이러한 수정 및 업데이트를 받을 수 있습니다.   |
| 차단 모드의 EDR(엔드포인트 감지 및 대응) | Microsoft 365 E5 | EDR 설정하면 장치의 기본 바이러스 백신 제품이 아닌 Microsoft Defender 바이러스 백신 보호 기능을 추가로 제공합니다. EDR 모드에서는 Microsoft가 아닌 기본 바이러스 백신 솔루션이 누락할 수 EDR 생성 검사 중에 발견된 아티팩트를 수정합니다. 기본 바이러스 백신 솔루션으로 Microsoft Defender 바이러스 백신 장치를 사용할 수 있는 경우 EDR 모드로 설정하면 EDR 검사 중에 식별된 아티팩트를 자동으로 수정하는 이점이 추가됩니다. <br/><br/>자세한 내용은 EDR [모드로 전환을 참조합니다.](edr-in-block-mode.md)|
| 공격 노출 영역 축소 규칙 | Microsoft 365 E5 또는 E3 | 공격 표면 감소는 조직 끝점이 사이버 공격에 취약한 위치와 방법을 줄이는 것입니다. 공격 표면 감소 규칙은 맬웨어를 중지하도록 구성할 수 있는 지능형 규칙입니다. 특정 규칙은 완벽하게 작동하기 위해 클라우드 보호를 켜야 합니다. 이러한 규칙은 다음과 같습니다. <br/>- 실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 조건을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단 <br/>- 랜섬웨어에 대한 고급 보호 사용 <br/>- 이동식 드라이브에서 트러스터가 실행되지 않는 프로그램 차단 <br/><br/>자세한 내용은 공격 표면 감소 규칙을 사용하여 맬웨어 [감염 방지를 참조합니다.](attack-surface-reduction.md)  |
| 손상 표시기(IoC) | Microsoft 365 E5  | 끝점용 Defender의 IoC는 엔터티의 검색, 방지 및 제외를 정의하도록 구성할 수 있습니다. 예를 들어 "허용" 표시기를 사용하여 끝점용 Defender에서 검사 Microsoft Defender 바이러스 백신 수정 작업에 대한 예외를 정의할 수 있습니다. 또 다른 예로 "경고 및 차단" 표시기를 사용하여 파일 또는 프로세스가 실행되지 않도록 방지하고, Microsoft 365 Defender 포털에서 볼 수 있는 경고로 이러한 활동을 추적할 수 있습니다. <br/><br/>자세한 내용은 [지표 만들기를 참조합니다.](manage-indicators.md)    |


## <a name="next-steps"></a>다음 단계

클라우드 보호에 대한 개요와 클라우드 보호의 역할이 Microsoft Defender 바이러스 백신 다음 단계는 다음과 같습니다.

1. **[클라우드 보호를 사용하도록 설정](enable-cloud-protection-microsoft-defender-antivirus.md)**. 클라우드 보호 기능을 사용하여 클라우드 보호를 사용하도록 Microsoft Endpoint Manager(현재는 Microsoft Endpoint Configuration Manager 및 Microsoft Intune), 그룹 정책 또는 PowerShell cmdlet을 사용할 수 있습니다.

2. **[클라우드 보호 수준을 지정합니다.](specify-cloud-protection-level-microsoft-defender-antivirus.md)** 클라우드 또는 그룹 정책을 사용하여 클라우드에서 제공하는 보호 수준을 Microsoft Endpoint Manager 있습니다. 보호 수준은 클라우드와 공유되는 정보의 양과 새 파일이 차단되는 정도에 영향을 미치게 됩니다.

3. **[에 대한 네트워크 연결을 구성하고 Microsoft Defender 바이러스 백신.](configure-network-connections-microsoft-defender-antivirus.md)** 클라우드 보호가 효과적으로 작동하려면 네트워크 및 끝점에서 연결할 수 있어야 하는 특정 Microsoft URL이 있습니다. 이 문서에는 방화벽 또는 네트워크 필터링 규칙을 통해 허용해야 하는 URL과 네트워크가 클라우드 보호에 제대로 등록되어 있는지 확인하기 위한 지침이 나열되어 있습니다.

4. **["모든 시 차단" 기능을 구성합니다.](configure-block-at-first-sight-microsoft-defender-antivirus.md)** "최초 차단" 기능은 기존의 보안 인텔리전스를 위해 시간을 기다리지 않고도 몇 초 이내에 새 맬웨어를 차단할 수 있습니다. 그룹 정책 또는 그룹 정책을 사용하여 Microsoft Endpoint Manager 수 있습니다.

5. **[클라우드 차단 시간 제한 기간을 구성합니다.](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)** Microsoft Defender 바이러스 백신 클라우드 보호 서비스를 쿼리하는 동안 의심스러운 파일이 실행되지 못하게 차단할 수 있습니다. 그룹 정책 또는 그룹 정책을 사용하여 파일이 실행되지 않도록 할 Microsoft Endpoint Manager 있습니다.
