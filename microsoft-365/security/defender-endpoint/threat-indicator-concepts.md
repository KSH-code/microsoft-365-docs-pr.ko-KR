---
title: 끝점용 Microsoft Defender의 위협 인텔리전스 개념 이해
description: 조직에 대한 사용자 지정 위협 경고를 만들고 끝점용 Microsoft Defender의 위협 인텔리전스에 대한 개념 학습
keywords: 위협 인텔리전스, 경고 정의, 손상 표시기, ioc
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0451d875f149a875872f5d5a32d3580015dbfb0e
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2021
ms.locfileid: "60804884"
---
# <a name="understand-threat-intelligence-concepts"></a>위협 인텔리전스 개념 이해

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-threatindicator-abovefoldlink)

고급 사이버 보안 공격은 여러 복잡한 악성 이벤트, 특성 및 상황 정보로 구성됩니다. 이러한 활동 중 의심스러운 활동의 식별 및 결정은 어려운 작업일 수 있습니다. 업계와 관련한 알려진 특성 및 비정상적 활동에 대한 지식은 관찰된 동작을 의심스러운 행동으로 부를 때를 아는 데 기본입니다.

이 Microsoft 365 Defender 조직에서 가능한 공격 활동을 추적하는 데 도움이 되는 사용자 지정 위협 경고를 만들 수 있습니다. 의심스러운 이벤트에 플래그를 지정하여 단서를 모아 공격 체인을 중지할 수 있습니다. 이러한 사용자 지정 위협 경고는 조직에만 표시될 뿐 추적하기 위해 설정한 이벤트에 플래그를 지정합니다.

사용자 지정 위협 경고를 만들기 전에 경고 정의 및 IOC(손상 표시기) 뒤에 있는 개념과 이러한 경고 간의 관계를 알아야 합니다.

## <a name="alert-definitions"></a>경고 정의
경고 정의는 가능한 사이버 보안 공격에 대한 조기 단서를 식별하는 데 총체적으로 사용할 수 있는 상황적 특성입니다. 이러한 지표는 일반적으로 공격자가 공격의 목표를 달성하기 위해 수행한 활동, 특징 및 작업의 조합입니다. 이러한 특성 조합을 모니터링하는 것은 공격에 대한 가시적 지점을 확보하고 공격자 목표에 도달하기 전에 이벤트 체인을 끊는 데 중요합니다.

## <a name="indicators-of-compromise-ioc"></a>손상 표시기(IOC)
IOC는 네트워크 또는 장치가 이미 위반된 것을 나타내는 개별적으로 알려진 악성 이벤트입니다. 경고 정의와 달리 이러한 표시기는 위반의 증거로 간주됩니다. 공격이 이미 수행되고 목표에 도달한(예: 유출) 후에 종종 볼 수 있습니다. IOC를 추적하는 것은 포렌식 조사 중에도 중요합니다. 공격 체인에 개입할 수 없는 경우도 있을 수 있습니다. 이러한 지표를 수집하면 향후의 공격에 대한 더 나은 방어를 만드는 데 유용할 수 있습니다.

## <a name="relationship-between-alert-definitions-and-iocs"></a>경고 정의와 IOC 간의 관계
Microsoft 365 Defender 및 끝점용 Microsoft Defender의 컨텍스트에서 경고 정의는 IOC에 대한 컨테이너로, 특정 IOC 일치에 대해 발생된 메타데이터를 포함하여 경고를 정의합니다. 경고 정의의 일부로 다양한 메타데이터가 제공됩니다. 공격의 경고 정의 이름, 심각도 및 설명과 같은 메타데이터가 다른 옵션과 함께 제공됩니다.

각 IOC는 유형, 값 및 작업을 기반으로 구체적인 검색 논리를 정의하여 일치 방법을 결정합니다. 검색이 검색 콘솔에서 경고로 표시되는 방법을 정의하는 특정 경고 Microsoft 365 Defender 바인딩됩니다.

다음은 IOC의 예입니다.
- 유형: Sha1
- 값: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- 동작: 같음

IOC는 경고 정의에 해당하는 여러 IOC가 될 수 있는 경고 정의와 다대일 관계를 맺습니다.


## <a name="related-topics"></a>관련 항목
- [지표 관리](manage-indicators.md)
