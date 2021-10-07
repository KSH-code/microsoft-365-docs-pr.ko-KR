---
title: Windows 서버 응용 프로그램 테스트
description: Windows Server 응용 프로그램 테스트를 사용하여 유효성을 검사하는 방법
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
ms.openlocfilehash: 99868e53e98bded9139ecedea9c9d62e9d48fd2f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211756"
---
# <a name="windows-server-application-testing"></a>Windows 서버 응용 프로그램 테스트

Test Base for Microsoft 365 Server Core를 포함하여 Windows Server 2016 및 2019에 대해 응용 프로그램의 유효성을 검사할 수 있습니다.

Windows Server 2016 및 2019 운영 체제의 시험판 업데이트에 대해 업로드된 응용 프로그램의 유효성을 검사하기 시작하려면 Microsoft 365 다음 단계를 따르세요.

1. 셀프 서비스 온보더링 포털에 로그온합니다. 왼쪽 탐색 메뉴에서 아래를 선택하고 테스트 `Upload new package` `Package catalogue` 세부 정보를 입력합니다.

2. `Security updates`OS 업데이트 유형으로 선택:

   ![보안 업데이트를 선택합니다.](Media/selecting-security-updates.png)

3. 테스트할 OS 버전에서 해당 OS 버전을 선택합니다. 서버 OS Windows 또는 서버 및 클라이언트 OS 버전 조합을 선택할 수 있습니다.

   ![OS 버전을 선택합니다.](Media/selecting-OS-versions.png)

4. 다른 필수 정보를 제공하고, 제공된 세부 정보를 검토하고, 응용 프로그램 패키지를 업로드합니다. 업로드한 후 패키지 관리 메뉴 탭에서 패키지 상태를 볼 수 있습니다.

5. Windows Server 2016 및 2019의 시험판 보안 업데이트에 대해 응용 프로그램의 유효성 검사에서 테스트 결과 및 인사이트를 확인한 다음 테스트 요약 페이지 또는 보안 업데이트 결과 페이지로 이동하세요.

   ![테스트 결과를 시청합니다.](Media/access-test-results.png)

기능 테스트 시작을 위해 다음 **문서로 진행**
> [!div class="nextstepaction"]
> [다음 단계](functional.md)
