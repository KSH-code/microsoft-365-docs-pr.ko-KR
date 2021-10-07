---
title: eDiscovery 검색 결과를 내보낼 때 PST 파일의 크기 변경
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: eDiscovery 검색 결과를 내보낼 때 컴퓨터에 다운로드되는 PST 파일의 기본 크기를 변경할 수 있습니다.
ms.openlocfilehash: b0376a423827df855af83375ddfae0e9803fd933
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158373"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>eDiscovery 검색 결과를 내보낼 때 PST 파일의 크기 변경

eDiscovery 내보내기 도구를 사용하여 다른 Microsoft eDiscovery 도구에서 eDiscovery 검색의 전자 메일 결과를 내보내는 경우 내보낼 수 있는 PST 파일의 기본 크기는 10GB입니다. 이 기본 크기를 변경하려면 검색 결과를 내보내는 데 사용하는 Windows 레지스트리를 편집할 수 있습니다. 이 작업을 하는 한 가지 이유는 PST 파일이 DVD, 컴팩트 디스크 또는 USB 드라이브와 같은 이동식 미디어에 맞을 수 있도록 하는 것입니다. 
  
> [!NOTE]
> eDiscovery 내보내기 도구는 검색 도구에서 콘텐츠 검색 도구를 사용할 때 검색 결과를 내보내는 데 Microsoft 365 규정 준수 센터.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>eDiscovery 검색 결과를 내보낼 때 PST 파일의 크기를 변경하는 레지스트리 설정 만들기

eDiscovery 검색 결과를 내보내는 데 사용할 컴퓨터에서 다음 절차를 수행하십시오.
  
1. eDiscovery 내보내기 도구가 열려 있는 경우 닫습니다. 
    
2. .reg의 파일 이름 접미사로 다음 텍스트를 Window 레지스트리 파일에 저장합니다. 예를 들어 PstExportSize.reg와 같습니다. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    위의 예제에서 값은  `PstSizeLimitInBytes` 1,073,741,824바이트 또는 약 1GB로 설정됩니다. 다음은 설정에 대한 몇 가지 다른 샘플  `PstSizeLimitInBytes` 값입니다. 
    
    |**크기(약 GB)**|**크기(bytes)**|
    |:-----|:-----|
    |0.7GB(700MB)  <br/> |751619277  <br/> |
    |2GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8GB  <br/> |8589934592  <br/> |
   
3. 검색 결과를 내보낼 때 값을 원하는 최대 PST 파일 크기로 변경한 다음 `PstSizeLimitInBytes` 파일을 저장합니다. 
    
4. Windows 탐색기에서 이전 단계에서 만든 .reg 파일을 클릭하거나 두 번 클릭합니다.
    
5. 사용자 액세스 제어 창에서 **예를** 클릭하여 레지스트리 편집기를 변경하도록 합니다. 
    
6. 계속할지 묻는 메시지가 표시될 때 예를 **클릭합니다.**
    
    레지스트리 편집기에는 설정이 레지스트리에 추가되었습니다는 메시지가 표시됩니다.
    
7. 3-6단계를 반복하여 레지스트리 설정 값을 변경할  `PstSizeLimitInBytes` 수 있습니다. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>eDiscovery 검색 결과를 내보낼 때 PST 파일의 기본 크기 변경에 대한 질문과 대답

 **기본 크기는 10GB인 이유는 무엇입니까?**
  
기본 크기인 10GB는 고객 의견을 기반으로 합니다. 10GB는 단일 PST에서 최적의 콘텐츠 양과 파일 손상 가능성이 가장 큰 균형입니다.
  
 **PST 파일의 기본 크기를 늘리거나 줄이세요?**
  
고객은 조직의 다른 위치로 물리적으로 발송할 수 있는 이동식 미디어에 검색 결과가 적합하게 크기 제한을 낮출 수 있습니다. 10GB보다 큰 PST 파일에 손상 문제가 있을 수 있기 때문에 기본 크기를 늘리지 않는 것이 좋습니다.
  
 **어떤 컴퓨터에서 이 작업을 해야 하나요?**
  
eDiscovery 내보내기 도구를 실행한 로컬 컴퓨터에서 레지스트리 설정을 변경해야 합니다.
  
 **이 설정을 변경한 후 컴퓨터를 다시 시작해야 하나요?**
  
아니요. 컴퓨터를 다시 시작하지는 않습니다. 그러나 eDiscovery 내보내기 도구가 실행 중인 경우 이 설정을 변경한 후 도구를 닫고 다시 시작해야 합니다.
  
 **기존 레지스트리 키가 편집되거나 새 키가 만들어지나요?**
  
이 절차에서 만든 .reg 파일을 처음 실행할 때 새 레지스트리 키가 만들어집니다. 그런 다음 .reg 편집 파일을 변경하고 다시 설정할 때마다 설정을 편집합니다.
