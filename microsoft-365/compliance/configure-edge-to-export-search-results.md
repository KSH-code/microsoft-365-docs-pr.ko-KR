---
title: eDiscovery 내보내기 도구는 Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 보안 및 ClickOnce 센터의 콘텐츠 검색 및 eDiscovery에서 검색 결과를 다운로드하려면 Microsoft Edge 최신 버전을 사용하도록 설정해야 합니다.
ms.openlocfilehash: bd42ebffce326e4abe4943ff4187fc2bd960ff65
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184268"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>eDiscovery 내보내기 도구는 Microsoft Edge

최신 버전의 Microsoft Edge 변경으로 인해 ClickOnce 지원이 더 이상 사용되지 않습니다. eDiscovery 내보내기 도구를 사용하여 콘텐츠 검색 또는 eDiscovery 검색 결과를 다운로드하려면 [Microsoft](https://support.microsoft.com/help/17621/internet-explorer-downloads) Internet Explorer 사용하여 최신 버전의 ClickOnce 지원을 사용하도록 설정해야 Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>사용자 ClickOnce 지원 Microsoft Edge

1. In Microsoft Edge, go to **edge://flags/#edge-click-once**.

2. 드롭다운 목록에서 기존 값을 **Default** 또는 **Disabled로** 설정하면 사용으로 **변경합니다.**

   ![드롭다운 목록에서 사용 을 선택합니다.](../media/ClickOnceimage1.png)

3. 브라우저 창 아래쪽으로 스크롤한 다음  다시 시작을 클릭하여 Edge를 다시 시작합니다.

   ![다시 시작을 클릭합니다.](../media/ClickOnceimage2.png)

**참고:** 조직에서는 그룹 정책을 사용하여 조직에서 지원을 사용하지 ClickOnce 있습니다. 조직 지원에 대한 조직 정책이 ClickOnce 으로 **edge://policy.** 다음 스크린샷은 전체 ClickOnce 사용하도록 설정되어 있습니다. 이 정책 값이 **false로** 설정된 경우 조직의 관리자에게 문의해야 합니다.

![에지 조직 정책 목록입니다.](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>eDiscovery 내보내기 도구 설치 및 실행

1. 콘텐츠 **검색 또는** eDiscovery 사례에서 내보내기 플라이아웃 페이지에서 결과 다운로드를 클릭합니다.

   ![플라이아웃 페이지에서 결과 다운로드를 클릭하여 검색 결과를 다운로드합니다.](../media/ClickOnceExport1.png)

2. 도구를 실행하라는 확인 메시지가 표시됩니다. 열기 를 **클릭합니다.**

   ![열기 를 클릭하여 eDiscovery 내보내기 도구를 실행합니다.](../media/ClickOnceimage4.png)

   eDiscovery 내보내기 도구가 설치되어 있지 않은 경우 보안 경고 메시지가 표시됩니다. 

   ![설치를 클릭하여 eDiscovery 내보내기 도구를 설치합니다.](../media/ClickOnceimage5.png)

3. **설치** 를 클릭합니다. 설치한 후 내보내기 도구가 자동으로 시작됩니다.

자세한 내용은 아래 항목을 참조하세요.

- [콘텐츠 검색 결과 내보내기](export-search-results.md)

- [사용자 지정에서 실험 플래그를 사용하도록 설정하는 Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
