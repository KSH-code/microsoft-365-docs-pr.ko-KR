---
title: 파일에 대한 표시기 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시에 대한 표시기를 만들 수 있습니다.
keywords: 파일, 해시, 관리, 허용, 차단, 차단, 정리, 악성, 파일 해시, ip 주소, URL, 도메인
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d78f90e78a50d5902070f441a1d60693a5f531c8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185722"
---
# <a name="create-indicators-for-files"></a>파일에 대한 표시기 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

잠재적인 악성 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 추가로 전파되는 것을 방지할 수 있습니다. 잠재적으로 악의적인 PE(이식 가능한 실행 파일) 파일을 알고 있는 경우 해당 파일을 차단할 수 있습니다. 이 작업을 수행하면 조직의 컴퓨터의 읽기, 작성 또는 실행이 차단됩니다.

파일에 대한 표시기를 만드는 방법에는 다음 두 가지가 있습니다.
- 설정 페이지를 통해 표시기를 만들어
- 파일 세부 정보 페이지에서 표시기 추가 단추를 사용하여 상황 표시기를 만들 수 있습니다.

### <a name="before-you-begin"></a>시작하기 전에
파일에 대한 표시기를 만들기 전에 다음과 같은 선행 방법을 이해하는 것이 중요합니다.

- 이 기능은 조직에서 바이러스 백신 및 클라우드 Windows Defender 사용하도록 설정된 경우 사용할 수 있습니다. 자세한 내용은 클라우드 제공 보호를 통해 Microsoft Defender 바이러스 백신에 [차세대 기술 사용을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- 맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.
- Windows 10 버전 1703 이상, Windows server 2016 및 2019의 컴퓨터에서 지원됩니다.
- 파일 차단을 시작하려면 먼저 설정에서 차단 또는 허용 [기능을 켜야  ](advanced-features.md) 합니다.
- 이 기능은 의심되는 맬웨어(또는 악성 파일)가 웹에서 다운로드되지 않도록 디자인되었습니다. 현재 _.exe_ 및 _.dll_ 파일을 비롯한 PE(이식 가능한 실행 파일) 파일을 지원하고 있습니다. 적용 범위는 시간이 지날 때 연장됩니다.

>[!IMPORTANT]
>- 허용 또는 차단 작업 전에 파일의 분류가 디바이스 캐시에 있는 경우 파일에서 허용 또는 차단 기능을 할 수 없습니다. 
>- 신뢰할 수 있는 서명된 파일은 다르게 처리됩니다. 끝점용 Defender는 악성 파일을 처리하도록 최적화되어 있습니다. 경우에 따라 신뢰할 수 있는 서명된 파일을 차단하려고 시도하면 성능에 의미가 있을 수 있습니다.

 
>[!NOTE]
>일반적으로 파일 블록은 몇 분 이내에 적용되지만 30분까지 걸릴 수 있습니다.

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>설정 페이지에서 파일에 대한 표시기 만들기

1. 탐색 창에서 설정   >  **표시기를 선택합니다.**  

2. 파일 **해시 탭을** 선택합니다.

3. 표시기 **추가를 선택합니다.**

4. 다음 세부 정보를 지정합니다.
   - Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.
   - 작업 - 수행될 작업을 지정하고 설명을 입력합니다.
   - 범위 - 컴퓨터 그룹의 범위를 정의합니다.

5. 요약 탭에서 세부 정보를 검토한 다음 저장을 **클릭합니다.**

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>파일 세부 정보 페이지에서 상황 표시기 만들기
파일에 대한 응답 작업을 수행할 때의 옵션 중 하나는 [파일에](respond-file-alerts.md) 대한 표시기를 추가하는 것입니다. 

파일에 대한 표시기 해시를 추가할 때 조직의 컴퓨터로 실행을 시도할 때마다 경고를 발생하고 파일을 차단할 수 있습니다.

표시기에서 자동으로 차단되는 파일은 파일의 알림 센터에 표시되지 않지만 경고 큐에 계속 표시됩니다.


## <a name="related-topics"></a>관련 항목
- [표시기 만들기](manage-indicators.md)
- [IPS 및 URL/도메인에 대한 표시기 만들기](indicator-ip-domain.md)
- [인증서를 기반으로 표시기 만들기](indicator-certificates.md)
- [표시기 관리](indicator-manage.md)
