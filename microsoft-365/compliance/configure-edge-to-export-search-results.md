---
title: Microsoft Edge에서 Office 365 eDiscovery 내보내기 도구 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 보안 및 준수 센터에서 콘텐츠 검색 및 eDiscovery의 검색 결과를 내보내려면 Microsoft Edge를 사용 하 여 ClickOnce 지원을 사용 하도록 설정 해야 합니다.
ms.openlocfilehash: db70b4cdbc57f519db3b6b962eb8aa43585ba335
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078591"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Microsoft Edge에서 Office 365 eDiscovery 내보내기 도구 사용

Microsoft Edge의 최근 변경 사항으로 인해 ClickOnce 지원은 더 이상 기본적으로 사용 되지 않도록 설정 되어 있습니다. Microsoft Office 365 eDiscovery 내보내기 도구를 계속 사용 하 여 콘텐츠 검색 또는 eDiscovery 검색 결과를 다운로드 하려면 [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) 를 사용 하거나 microsoft Edge에서 ClickOnce 지원을 사용 해야 합니다.

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>Microsoft Edge에서 ClickOnce 지원을 사용 하도록 설정 하는 방법

1. Microsoft Edge에서 **edge://flags/#edge-클릭 한 번**으로 이동 합니다.

2. 기존 값이 드롭다운 목록에서 **기본값** 또는 **사용 안** 함으로 설정 되어 있으면 **사용**으로 변경 합니다.
    
   ![](../media/ClickOnceimage1.png)

3. 브라우저 창의 아래쪽으로 스크롤한 다음 **다시 시작** 을 클릭 하 여 Edge를 다시 시작 합니다.

   ![](../media/ClickOnceimage2.png)

**참고:** 조직에서는 그룹 정책을 사용 하 여 ClickOnce 지원을 사용 하지 않도록 설정할 수 있습니다. ClickOnce 지원에 대 한 조직 정책이 있는지 확인 하려면 **edge://policy**로 이동 합니다. 다음 스크린샷에서는 전체 조직에서 ClickOnce가 사용 되도록 설정 되어 있음을 보여 줍니다. 이 정책 값이 **false**로 설정 된 경우 조직의 관리자에 게 문의 해야 합니다.

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>Office 365 eDiscovery 내보내기 도구 설치 및 실행

1. 콘텐츠 검색 또는 eDiscovery 사례에서 내보내기의 플라이 아웃 페이지에서 **결과 다운로드** 를 클릭 합니다.

   ![검색 결과를 다운로드 하려면 플라이 아웃 페이지에서 결과 다운로드를 클릭 합니다.](../media/ClickOnceExport1.png)

2. 도구를 시작할 것인지 묻는 메시지가 표시 되 면 **열기**를 클릭 합니다.

   ![열기를 클릭 하 여 eDiscovery 내보내기 도구를 시작 합니다.](../media/ClickOnceimage4.png)

   Microsoft Office 365 eDiscovery 내보내기 도구가 설치 되어 있지 않으면 보안 경고를 표시 합니다. 

   ![EDiscovery 내보내기 도구를 설치 하려면 설치를 클릭 합니다.](../media/ClickOnceimage5.png)

3. **설치**를 클릭합니다. 설치가 완료 되 면 내보내기 도구가 자동으로 실행 됩니다.

자세한 내용은 다음 항목을 참조하세요.

- [콘텐츠 검색 결과 내보내기](export-search-results.md)

- [Microsoft Edge에서 실험 플래그를 사용 하도록 설정 하는 방법](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
