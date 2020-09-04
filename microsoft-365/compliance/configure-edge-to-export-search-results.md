---
title: Microsoft Edge에서 eDiscovery 내보내기 도구 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 보안 및 준수 센터에서 콘텐츠 검색 및 eDiscovery의 검색 결과를 다운로드 하려면 최신 버전의 Microsoft Edge를 사용 하려면 ClickOnce 지원을 사용 하도록 설정 해야 합니다.
ms.openlocfilehash: 317e19c81a606565fcb18f3256fd5bac007747e1
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357578"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Microsoft Edge에서 eDiscovery 내보내기 도구 사용

최신 버전의 Microsoft Edge에 대 한 최근 변경 사항으로 인해 ClickOnce 지원 기능은 더 이상 기본적으로 사용 되지 않도록 설정 되어 있습니다. EDiscovery 내보내기 도구를 계속 사용 하 여 콘텐츠 검색 또는 eDiscovery 검색 결과를 다운로드 하려면 [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) 를 사용 하거나 최신 버전의 microsoft Edge에서 ClickOnce 지원을 사용 하도록 설정 해야 합니다.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Microsoft Edge에서 ClickOnce 지원 사용

1. Microsoft Edge에서 **edge://flags/#edge-클릭 한 번**으로 이동 합니다.

2. 기존 값이 드롭다운 목록에서 **기본값** 또는 **사용 안** 함으로 설정 되어 있으면 **사용**으로 변경 합니다.

   ![드롭다운 목록에서 사용을 선택 합니다.](../media/ClickOnceimage1.png)

3. 브라우저 창의 아래쪽으로 스크롤한 다음 **다시 시작** 을 클릭 하 여 Edge를 다시 시작 합니다.

   ![다시 시작 클릭](../media/ClickOnceimage2.png)

**참고:** 조직에서는 그룹 정책을 사용 하 여 ClickOnce 지원을 사용 하지 않도록 설정할 수 있습니다. ClickOnce 지원에 대 한 조직 정책이 있는지 확인 하려면 **edge://policy**로 이동 합니다. 다음 스크린샷에서는 전체 조직에서 ClickOnce가 사용 되도록 설정 되어 있음을 보여 줍니다. 이 정책 값이 **false**로 설정 된 경우 조직의 관리자에 게 문의 해야 합니다.

![에 지 조직 정책 목록](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>EDiscovery 내보내기 도구 설치 및 실행

1. 콘텐츠 검색 또는 eDiscovery 사례에서 내보내기의 플라이 아웃 페이지에서 **결과 다운로드** 를 클릭 합니다.

   ![검색 결과를 다운로드 하려면 플라이 아웃 페이지에서 결과 다운로드를 클릭 합니다.](../media/ClickOnceExport1.png)

2. 도구를 시작할 것인지 묻는 메시지가 표시 되 면 **열기**를 클릭 합니다.

   ![열기를 클릭 하 여 eDiscovery 내보내기 도구를 시작 합니다.](../media/ClickOnceimage4.png)

   EDiscovery 내보내기 도구가 설치 되어 있지 않으면 보안 경고를 표시 합니다. 

   ![EDiscovery 내보내기 도구를 설치 하려면 설치를 클릭 합니다.](../media/ClickOnceimage5.png)

3. **설치**를 클릭합니다. 설치가 완료 되 면 내보내기 도구가 자동으로 실행 됩니다.

자세한 내용은 아래 항목을 참조하세요.

- [콘텐츠 검색 결과 내보내기](export-search-results.md)

- [Microsoft Edge에서 실험 플래그를 사용 하도록 설정 하는 방법](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
