---
title: 공격 시뮬레이션 교육을 위한 페이로드 자동화
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 페이로드 자동화(페이로드 수집)를 사용하여 Microsoft Defender for Office 365 계획에서 공격 시뮬레이션 교육을 위한 자동화된 시뮬레이션을 수집하고 Office 365 있습니다.
ms.technology: mdo
ms.openlocfilehash: 0e090b79c8e04de5f0e9e81449d805d2b124bc59
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717622"
---
# <a name="payload-automations-for-attack-simulation-training"></a>공격 시뮬레이션 교육을 위한 페이로드 자동화

**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)

Microsoft 365 E5 또는 Office 365 Plan 2용 Microsoft Defender의 공격 시뮬레이션 교육에서 페이로드 자동화(페이로드 수집)는 조직의 사용자가 보고한 실제 피싱 메시지에서 정보를 수집합니다.  이러한 메시지의 수는 조직에서 적을 가능성이 높지만 피싱 공격에서 검색할 조건(예: 받는 사람, 소셜 엔지니어링 기술, 보낸 사람 정보 등)을 지정할 수 있습니다. 그런 다음 공격 시뮬레이션 교육은 공격에 사용된 메시지 및 페이로드를 모방하여 대상 사용자에게 무해한 시뮬레이션을 자동으로 실행합니다.

페이로드 자동화를 만들 경우 다음 단계를 수행합니다.

1. 의 Microsoft 365 Defender 포털에서 전자 메일 & 공격 시뮬레이션 <https://security.microsoft.com/>  \> **교육** \> **페이로드 자동화 탭으로 이동하세요.**

   페이로드 자동화 **탭으로** 직접 이동하기 위해 를 <https://security.microsoft.com/attacksimulator?viewid=payloadautomation> 사용합니다.

2. 페이로드 **자동화 탭에서** 시뮬레이션 ![ 만들기 아이콘을 선택합니다.](../../media/m365-cc-sc-create-icon.png) **시뮬레이션을 생성합니다.**

   ![웹 포털의 공격 시뮬레이션 교육에서 페이로드 자동화 탭에 시뮬레이션 단추를 Microsoft 365 Defender.](../../media/attack-sim-training-sim-automations-create.png)

3. 만들기 마법사가 열립니다. 이 문서의 나머지부분에서는 페이지 및 페이지에 포함된 설정에 대해 설명합니다.

> [!NOTE]
> 시뮬레이션 만들기 마법사 중 어느 시점에서든 저장 및 닫기 를 클릭하여 진행률을 저장하고 나중에 시뮬레이션을 계속 구성할 수 있습니다.  불완전한 시뮬레이션의  상태  값은 시뮬레이션 탭에 **임시로** 표시됩니다. 시뮬레이션을 선택하고 시뮬레이션 편집 아이콘을 클릭하여 떠날 위치를 선택할 ![ 수 있습니다.](../../media/m365-cc-sc-edit-icon.png) **simulation.##** 이름을 편집하고 시뮬레이션을 설명합니다.

## <a name="automation-name"></a>자동화 이름

자동화 **이름 페이지에서** 다음 설정을 구성합니다.

- **이름:** 시뮬레이션을 설명하는 고유한 이름을 입력합니다.
- **설명:** 시뮬레이션에 대한 선택적 자세한 설명을 입력합니다.

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="run-conditions"></a>실행 조건

실행 **조건 페이지에서** 자동화가 실행되는 경우를 결정하는 실제 피싱 공격의 조건을 선택합니다.

각 조건은 한 번만 사용할 수 있습니다. 여러 조건은 AND 논리( \<Condition1\> 및 )를 \<Condition2\> 사용합니다.

![조건 아이콘을 추가합니다.](../../media/m365-cc-sc-create-icon.png) **조건을 추가합니다.**

- **아니요. 캠페인 대상 사용자:** 다음 설정을 구성합니다.
  - **,** 보다 **작음**, **보다 크거나** **같음**, 보다 작거나 같음 또는 **보다 크거나 같음**
  - **Enter value:** 피싱 캠페인을 대상으로 한 사용자 수입니다.
- **특정 피싱 기술을** 사용하여 캠페인: 사용 가능한 값 중 하나를 선택합니다.
  - **자격 증명 수집**
  - **맬웨어 첨부 파일**
  - **첨부 파일 링크**
  - **맬웨어 링크**
  - **URL 드라이브**
- **특정 보낸 사람 도메인**: 보낸 사람 전자 메일 도메인 값(예: contoso.com)을 입력합니다.
- **특정 보낸 사람 이름:** 보낸 사람 이름 값을 입력합니다.
- **특정 보낸 사람 전자 메일:** 보낸 사람 전자 메일 주소를 입력합니다.
- **특정 사용자 및 그룹 받는 사람:** 사용자 또는 그룹의 이름 또는 전자 메일 주소를 입력하기 시작하세요. 표시가 나타나면 선택합니다.

조건을 추가한 후 제거하려면 ![제거 아이콘.](../../media/m365-cc-sc-delete-icon.png).

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="review-automation"></a>자동화 검토

자동화 **검토 페이지에서** 페이로드 자동화의 세부 정보를 검토할 수 있습니다.

각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다. 또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.

작업을 마쳤으면 **제출** 을 클릭합니다.
