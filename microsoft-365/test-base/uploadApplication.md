---
title: 업로드 패키지 관리
description: 테스트 베이스에 응용 프로그램, 이진 및 종속성 업로드 방법
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 2bda97c9168f7d3162c07ece4629dad795645638
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154137"
---
# <a name="step-2-uploading-a-package"></a>2단계: 패키지 업로드

테스트 기본 포털 페이지에서 아래  업로드 탐색 모음의 새 패키지 옵션으로 이동합니다.

:::image type="content" alt-text="업로드 패키지를 추가합니다." source="Media/Upload-New-Package.png" lightbox="Media/Upload-New-Package.png":::

이 단계에 따라 새 패키지를 업로드합니다.

## <a name="enter-details-for-your-package"></a>패키지에 대한 세부 정보 입력

테스트 세부 정보 탭에서 요청에 따라 패키지의 이름, 버전 및 기타 세부 정보를 입력합니다.

**이 대시보드를 통해 Out-of-Box** 및 **Functional 테스트를** 완료할 수 있습니다.

아래 단계에서는 패키지 세부 정보를 작성하는 방법에 대한 가이드를 제공합니다.

1. 필드에 패키지에 지정될 이름을 `Package name` 입력합니다.

    > [!NOTE]
    > 입력한 패키지 이름 및 버전 조합은 조직 내에서 고유해야 합니다. 아래와 같이 확인 표시에 의해 유효성이 검사됩니다.

    - 패키지의 이름을 다시 사용하려면 버전 번호가 고유해야 합니다(즉, 특정 이름을 사용하는 패키지와 함께 사용되지 않은 경우).

    - 패키지 이름 + 버전 조합이 고유성 검사를 통과하지 못하면 "이 패키지 버전이 있는 패키지가 이미 *있습니다."라는* 오류 메시지가 표시됩니다.

    :::image type="content" alt-text="패키지 지침을 업로드하기 위한 이미지입니다." source="Media/Instructions.png":::

2. "패키지 버전" 필드에 버전을 입력합니다.

    :::image type="content" alt-text="패키지 버전." source="Media/ApplicationVersion.png":::

3. 이 패키지에서 실행할 테스트 유형을 선택합니다.

    **OOB(Out-of-Box)** 테스트는 패키지 *설치,* *실행,*  닫기 및 제거를 실행합니다.  설치 후 단일 제거가 실행되기 전에 시작 닫기 루틴이 30번 반복됩니다.

    이 OOB 테스트는 패키지에 대한 표준화된 원격 분석 기능을 제공하여 여러 빌드에서 Windows 제공합니다.

    기능 **테스트는** 패키지에 업로드된 테스트 스크립트를 실행합니다. 스크립트는 업로드 순서대로 실행되고 특정 스크립트에서 오류가 발생하면 후속 스크립트 실행이 중지됩니다.

    > [!NOTE]
    > **모든** 스크립트는 가장 80분 동안 실행됩니다.

4. OS 업데이트 유형을 선택합니다.

    - '보안 업데이트'를 사용하면 릴리스 전 월간 보안 업데이트의 증분 Windows 테스트할 수 있습니다.
    - '기능 업데이트'를 사용하면 Windows 프로그램 내부자 프로그램에서 시험판 기능 업데이트 빌드를 Windows 테스트할 수 있습니다.
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="OS 업데이트 유형입니다." source="Media/OSUpdateType.png":::

5. 보안 업데이트 테스트용 OS 버전을 선택합니다.

    다중 선택 드롭다운에서 패키지가 설치될 Windows OS 버전을 선택합니다.

    - 클라이언트 운영 Windows 대해 패키지를 테스트하려면 메뉴 목록에서 해당 Windows 11 OS 버전을 선택합니다.
    - Windows Server 운영 체제에서만 패키지를 테스트하려면 메뉴 목록에서 Windows Server OS 버전을 선택합니다.
    - Windows 및 Windows 서버 운영 체제에 대해 패키지를 테스트하려면 메뉴 목록에서 적용 가능한 모든 운영 체제를 선택합니다.

    > [!NOTE]
    > 서버 및 클라이언트 OSes 둘 다에 대해 패키지를 테스트하기로 선택한 경우 패키지가 호환되는지와 두 OS 모두에서 실행할 수 있는지 확인

    :::image type="content" alt-text="OS 버전 선택" source="Media/OSVersion.png":::
    <!---
    Change to the correct picture
    -->

6. 기능 업데이트 테스트에 대한 옵션을 선택합니다.

    - "내부자 채널 선택" 옵션에서 패키지를 테스트해야 하는 빌드로 `Windows Insider Program Channel` 선택합니다.

      현재 Insider Beta 채널에서 플라이트된 빌드를 사용 중입니다.

    - "인사이트에 대한 OS 기준 선택" 옵션에서 테스트 결과를 비교할 Windows 기준으로 사용할 Windows OS 버전을 선택합니다.

    > [!NOTE]
    > 현재는 서버 OS에 대한 기능 업데이트 테스트를 지원하지 않습니다.
    <!---
    Note to actual note format for markdown
    -->
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="기능 업데이트 테스트." source="Media/FeatureUpdate.png":::

7. 완료된 테스트 세부 정보 페이지는 다음과 같습니다.

    :::image type="content" alt-text="테스트 세부 정보 보기" source="Media/TestDetails.png":::

## <a name="next-steps"></a>다음 단계

다음 문서에서는 서비스에 이진 파일을 업로드하는 방법을 다루고 있습니다.

> [!div class="nextstepaction"]
> [다음 단계](binaries.md)

<!---
Add button for next page
-->
