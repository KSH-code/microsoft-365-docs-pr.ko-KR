---
title: 자동화 폴더 제외 관리
description: 자동화 폴더 제외를 추가하여 자동화된 조사에서 제외된 파일을 제어합니다.
keywords: 관리, 자동화, 제외, 차단, 정리, 악의적
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 09bd7b0318169e69e91a511c9d27033c5aeb0efa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151983"
---
# <a name="manage-automation-folder-exclusions"></a>자동화 폴더 제외 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

자동화 폴더 제외를 사용하면 자동화된 조사에서 건너뛸 폴더를 지정할 수 있습니다.

건너뛴 폴더에 대한 다음 특성을 제어할 수 있습니다.

- **폴더:** 건너뛴 폴더와 해당 하위 폴더를 지정할 수 있습니다.

  > [!NOTE]
  > 현재는 디렉터리에서 파일을 제외하는 방법으로 와일드카드를 사용할 수 없습니다.

- **파일의 확장명:** 특정 디렉터리에서 제외할 확장명을 지정할 수 있습니다. 확장은 공격자가 제외된 폴더를 사용하여 악용을 숨기는 것을 방지하는 한 가지 방법입니다. 확장명은 무시할 파일을 명시적으로 정의합니다.

- **파일 이름:** 특정 디렉터리에서 제외할 파일 이름을 지정할 수 있습니다. 이 이름은 공격자가 제외된 폴더를 사용하여 악용을 숨기지 못하게 하는 한 가지 방법입니다. 이름은 무시할 파일을 명시적으로 정의합니다.

## <a name="add-an-automation-folder-exclusion"></a>자동화 폴더 제외 추가

1. 탐색 창에서 **끝점** 규칙 설정 폴더 제외를 \>  \>  \> **선택합니다.**

2. 새 **폴더 제외 를 클릭합니다.**

3. 폴더 세부 정보를 입력합니다.

    - 폴더
    - 확장
    - 파일 이름
    - 설명

4. **저장** 을 클릭합니다.

> [!NOTE]
> 제외된 파일을 수집하거나 검사하기 위해 라이브 응답 명령은 오류와 함께 실패합니다. "파일이 제외됩니다." 또한 자동화된 조사는 제외된 항목을 무시합니다.

## <a name="edit-an-automation-folder-exclusion"></a>자동화 폴더 제외 편집

1. 탐색 창에서 **끝점** 규칙 설정 폴더 제외를 \>  \>  \> **선택합니다.**
2. 폴더 **제외에서** 편집을 클릭합니다.
3. 규칙의 세부 정보를 업데이트하고 저장을 **클릭합니다.**

## <a name="remove-an-automation-folder-exclusion"></a>자동화 폴더 제외 제거

1. 탐색 창에서 **끝점** 규칙 설정 폴더 제외를 \>  \>  \> **선택합니다.**
2. 제외 **제거를 클릭합니다.**

## <a name="related-topics"></a>관련 항목

- [자동화 허용/차단 목록 관리](manage-indicators.md)
- [자동화 파일 업로드 관리](manage-automation-file-uploads.md)
