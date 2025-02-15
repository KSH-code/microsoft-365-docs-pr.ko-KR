---
title: 업로드 응용 프로그램 이진
description: M365용 테스트 기준을 사용하여 시작하는 방법
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 200da9ca73bc666f3f11fc3fda95493d2c0954fb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180642"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>3단계: 업로드, 종속성 및 스크립트 확인

이 탭에서 테스트 제품군을 실행하는 데 사용되는 이진, 종속성 및 스크립트가 포함된 단일 zip 패키지를 업로드합니다.

> [!NOTE]
> zip 패키지의 크기는 최소 10MB에서 최대 2GB 사이입니다.

## <a name="upload-package-zip-file"></a>업로드 zip 파일

:::image type="content" alt-text="업로드 이진을 추가합니다." source="Media/AddBinaries.png":::

  - 업로드된 종속성에는 응용 프로그램 또는 테스트 사례를 실행하기 위해 액세스할 테스트 프레임워크, 스크립팅 엔진 또는 데이터가 포함됩니다. 예를 들어 Selenium 및 웹 드라이버 설치 관리자를 업로드하여 브라우저 기반 테스트를 실행할 수 있습니다.
  - 스크립트 활동이 모듈식으로 유지되도록 하는 것이 가장 좋은 예입니다. 
    - 스크립트는 `Install` 설치 작업만 수행됩니다.
    - 스크립트는 `Launch` 응용 프로그램만 실행합니다.
    - 스크립트는 `Close` 응용 프로그램만 닫습니다.
    - 선택적 `Uninstall` 스크립트는 응용 프로그램만 제거합니다.

**현재 포털에서는 PowerShell 스크립트만 지원됩니다.**


## <a name="next-steps"></a>다음 단계 

다음 문서로 이동하여 4단계: 테스트 작업 **설정으로 이동하세요.**
> [!div class="nextstepaction"]
> [돌아 가](uploadApplication.md)
> [!div class="nextstepaction"]
> [다음 단계](testtask.md)

