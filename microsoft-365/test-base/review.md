---
title: 검토
description: 온보드 후 섹션을 검토합니다.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323286"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>6단계: 선택을 검토하여 패키지를 만들 수 있습니다.

1.  이 탭에서 서비스에서는 테스트 세부 정보를 표시하고 빠른 완성도 검사를 실행합니다. 

    A ```Validation passed``` 또는 ```Validation failed``` 메시지는 다음 단계로 진행할 수 있는지 여부를 보여줍니다.

2.  테스트 세부 정보를 검토하고 충족하면 단추를 ```Create``` 클릭합니다. 

![유효성 검사 보기](Media/validation.png)

3.  이렇게 하면 패키지가 테스트 기준 환경에 온보드됩니다. 패키지가 성공적으로 만들어진 경우 Azure에서 패키지를 성공적으로 실행할 수 있는지 여부를 확인하는 자동화된 테스트가 트리거됩니다.

![성공한 결과](Media/successful.png)

> [!Note]
> Azure Portal에서 패키지 확인의 성공 또는 실패를 알리는 알림을 받을 수 있습니다. 
>
> 프로세스는 최대 24시간이 걸릴 수 있으므로 웹 페이지가 활성화되지 않은 경우 웹 페이지 시간 제한이 있을 수 있으므로 이 주문형 실행이 완료된 것을 알리지 않습니다. 

  - 이러한 상황이 발생하면 탭에서 패키지의 상태를 볼 수 ```Manage packages``` 있습니다.

![패키지 관리 이미지](Media/managepackages.png)

  - 테스트의 경우 예약된 간격으로 및 페이지를 통해 결과를 확인할 수 있으며 업로드한 후 며칠 후에 ```Test Summary``` ```Security Updates Results``` ```Feature Updates Results``` 시작되는 경우가 종종 있습니다.
  
  - 테스트에 실패한 동안 새 패키지를 업로드해야 합니다. 
  
    의 및 페이지에서 추가 분석을 ```test logs``` 위해 를 ```Security update results``` 다운로드할 수 ```Feature updates results``` 있습니다.

  - 반복적인 테스트 오류가 발생하는 경우 오류에 대한 세부 testbasepreview@microsoft.com 문의하세요. 

## <a name="next-steps"></a>다음 단계

아래 링크를 통해 콘텐츠 지침을 검색합니다.
> [!div class="nextstepaction"]
> [다음 단계](contentguideline.md)
