---
title: 끝점 계획 1에 대한 Microsoft Defender 관리(미리 보기)
description: Endpoint Plan 1에 대한 Defender를 유지 관리하고 업데이트합니다. 설정을 관리하고, 업데이트를 다운로드하고, 가을 긍정/음수 문제를 해결합니다.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 08/30/2021
ms.prod: m365-security
ms.technology: mde
localization_priority: Normal
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.openlocfilehash: c74549579efc9ddf94aa89cfe2007620ddd2d826
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214875"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1-preview"></a>끝점 계획 1에 대한 Microsoft Defender 관리(미리 보기)

> [!TIP]
> 아직 Microsoft 365 E3 없는 Microsoft 365 E5 미리 보기 프로그램에 [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) 등록하세요!

조직에서 끝점 계획 1(미리 보기)에 Defender를 사용할 때 보안 팀은 보안 솔루션을 유지 관리하기 위한 특정 단계를 취할 수 있습니다. 보안 팀에서 유지 관리 및 운영 계획을 수립할 때 최소한 다음 활동을 포함해야 합니다.

- [보안 인텔리전스 및 제품 업데이트 관리](#manage-security-intelligence-and-product-updates)
- [끝점에 맞게 Defender 미세 조정 및 조정](#fine-tune-and-adjust-defender-for-endpoint)
- [가짓 긍정/음수 해결](#address-false-positivesnegatives)

> [!IMPORTANT]
> 이 문서의 일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 시판된 제품/서비스와 관련이 있습니다. Microsoft는 여기에 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다. 이 문서에는 Defender for Endpoint Plan 1(미리 보기)에 포함되지 않은 일부 기능을 설명할 수 있는 온라인 콘텐츠에 대한 링크가 포함되어 있습니다.

## <a name="manage-security-intelligence-and-product-updates"></a>보안 인텔리전스 및 제품 업데이트 관리

최신 Microsoft Defender 바이러스 백신 유지하는 것은 새로운 맬웨어 및 공격 기술로부터 보호하는 데 중요합니다. Microsoft는 보안 인텔리전스, 바이러스 백신 및 맬웨어 방지 보호에 대한 정기 업데이트를 출시합니다. 업데이트는 두 가지 범주로 구성됩니다. 

- 보안 인텔리전스 업데이트
- 제품 업데이트 

보안 인텔리전스 및 제품 업데이트를 관리하기 위해 Microsoft Defender 바이러스 백신 및 기준 [적용을 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>끝점에 맞게 Defender 미세 조정 및 조정

Endpoint용 Defender는 많은 유연성과 구성 옵션을 제공합니다. 조직의 요구 사항에 맞게 설정을 조정하고 미세 조정할 수 있습니다. 예를 들어 그룹 정책 및 Microsoft Endpoint Manager 방법을 사용하여 끝점 보안 설정을 관리할 수 있습니다. 

자세한 내용은 [Endpoint용 Defender 관리를 참조합니다.](manage-atp-post-migration.md)

## <a name="address-false-positivesnegatives"></a>가짓 긍정/음수 해결

가짓 긍정은 실제로 위협이 아닌 경우에도 악성으로 감지된 파일 또는 프로세스와 같은 아티팩트입니다. 거짓 부정은 실제로 위협으로 검색되지 않은 엔터티입니다. 끝점용 Defender를 포함하여 모든 끝점 보호 솔루션에서 가짓 긍정/음수가 발생할 수 있습니다. 그러나 다음 그림과 같이 이러한 종류의 문제를 해결하고 솔루션을 세부적으로 조정하기 위해 취할 수 있는 단계가 있습니다.

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="가짓 긍정 및 음수 프로세스 개요":::

Endpoint용 Defender에 가짓 긍정/부정이 표시될 경우 [끝점용 Microsoft Defender에서 가짓](defender-endpoint-false-positives-negatives.md)긍정/음의 주소를 참조하세요.

## <a name="next-steps"></a>다음 단계

- [끝점용 Microsoft Defender의 새로운 제품 보기](whats-new-in-microsoft-defender-atp.md)