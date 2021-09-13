---
title: 콘텐츠 검색 결과를 내보낼 때 보고서를 사용하지 않도록 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: 로컬 Windows 콘텐츠 검색의 결과를 내보낼 때 보고서를 사용하지 않도록 설정하려면 로컬 컴퓨터의 Microsoft 365 규정 준수 센터.
ms.openlocfilehash: efe9ea768b68524dbfda003796a10d60453862bc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59193159"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>콘텐츠 검색 결과를 내보낼 때 보고서를 사용하지 않도록 설정

eDiscovery 내보내기 도구를 사용하여 콘텐츠 검색의 결과를 Microsoft 365 규정 준수 센터 내보낼 때 이 도구는 내보낼 콘텐츠에 대한 추가 정보가 포함된 두 개의 보고서를 자동으로 만들고 내보낼 수 있습니다. 이러한 보고서는 Results.csv 파일 및 Manifest.xml 파일입니다(이러한 [](#frequently-asked-questions-about-disabling-export-reports) 보고서에 대한 자세한 내용은 이 항목의 내보내기 보고서 사용 안 에 대한 질문과 대답 섹션 참조). 이러한 파일은 매우 크기 때문에 이러한 파일을 내보내지 못하게 하여 다운로드 시간을 절약하고 디스크 공간을 절약할 수 있습니다. 검색 결과를 내보내는 데 사용하는 Windows 레지스트리를 변경하여 이 작업을 할 수 있습니다. 나중에 보고서를 포함하려는 경우 레지스트리 설정을 편집할 수 있습니다. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>레지스트리 설정을 만들어 보고서 내보내기 기능을 사용하지 않도록 설정

콘텐츠 검색 결과를 내보내는 데 사용할 컴퓨터에서 다음 절차를 수행하십시오.
  
1. eDiscovery 내보내기 도구가 열려 있는 경우 닫습니다.
    
2. 사용하지 않도록 설정할 내보내기 보고서에 따라 다음 단계 중 하나 또는 둘 다를 수행합니다.
    
    - **Results.csv**
    
      파일 이름 접미사 .reg를 사용하여 Windows 레지스트리 파일에 다음 텍스트를 저장합니다. 예를 들어 DisableResultsCsv.reg와 같습니다.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      파일 이름 접미사 .reg를 사용하여 Windows 레지스트리 파일에 다음 텍스트를 저장합니다. 예를 들어 DisableManifestXml.reg와 같습니다.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. Windows 탐색기에서 이전 단계에서 만든 .reg 파일을 클릭하거나 두 번 클릭합니다.
    
4. 사용자 액세스 제어 창에서 **예를** 클릭하여 레지스트리 편집기를 변경하도록 합니다. 
    
5. 계속할지 묻는 메시지가 표시될 때 예를 **클릭합니다.**
    
    레지스트리 편집기에는 설정이 레지스트리에 추가되었습니다는 메시지가 표시됩니다.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>레지스트리 설정을 편집하여 내보내기 보고서를 다시 사용하도록 설정

이전 절차에서 .reg 파일을 만들어 Results.csv 및 Manifest.xml 보고서를 사용하지 않도록 설정한 경우 해당 파일을 편집하여 검색 결과로 내보낼 수 있도록 보고서를 다시 사용하도록 설정할 수 있습니다. 다시 콘텐츠 검색 결과를 내보내는 데 사용할 컴퓨터에서 다음 절차를 수행하십시오.
  
1. eDiscovery 내보내기 도구가 열려 있는 경우 닫습니다.
    
2. 이전 절차에서 만든 .reg 편집 파일 중 하나 또는 둘 다를 편집합니다.
    
    - **Results.csv**
    
        DisableResultsCsv.reg 메모장 를 열고 값을 로 변경한 `False` `True` 다음 파일을 저장합니다. 예를 들어 파일을 편집한 후 다음과 같이 표시됩니다.
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        DisableManifestXml.reg 메모장 를 열고 값을 로 변경한 `False` `True` 다음 파일을 저장합니다. 예를 들어 파일을 편집한 후 다음과 같이 표시됩니다.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. Windows 탐색기에서 이전 단계에서 편집한 .reg 파일을 클릭하거나 두 번 클릭합니다.
    
4. 사용자 액세스 제어 창에서 **예를** 클릭하여 레지스트리 편집기를 변경하도록 합니다. 
    
5. 계속할지 묻는 메시지가 표시될 때 예를 **클릭합니다.**
    
    레지스트리 편집기에는 설정이 레지스트리에 추가되었습니다는 메시지가 표시됩니다.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>내보내기 보고서를 사용 안 하게 하는 경우와 관련한 질문과 대답

 **보고서 및 Results.csv Manifest.xml 무엇입니까?**
  
파일 Results.csv Manifest.xml 파일에는 내보낼 콘텐츠에 대한 추가 정보가 포함되어 있습니다.
  
- **Results.csv** 검색 Excel 다운로드하는 각 항목에 대한 정보가 포함된 문서입니다. 전자 메일의 경우 결과 로그에는 다음을 비롯한 각 메시지에 대한 정보가 포함되어 있습니다. 
    
  - 원본 사서함에 있는 메시지의 위치 (포함 여부는 주 메시지는 보관 사서함 또는).
    
  - 메시지가 전송된 날짜
    
  - 메시지의 제목 줄입니다.
    
  - 보낸 사람 및 메시지 받는 사람입니다.
    
  - 검색 결과를 내보낼 때 중복 제거를 사용하도록 설정한 경우 메시지가 중복 메시지인지 여부입니다. 중복 메시지의 경우 상위 **ItemId** 열에서 해당 메시지를 중복 메시지로 식별하는 값이 있습니다. **Parent ItemId** 열의 값은 내보낼 메시지의 **Item DocumentId** 열 값과 동일합니다. 
    
    사이트 및 SharePoint 비즈니스용 OneDrive 문서의 경우 결과 로그에는 다음을 비롯한 각 문서에 대한 정보가 들어 있습니다.
    
  - 문서에 대 한 URL입니다.
    
  - 문서가 있는 사이트 모음의 URL입니다.
    
  - 문서를 마지막으로 수정한 날짜입니다.
    
  - 이름 (에 있는 제목 열 결과 로그에서) 문서입니다.
    
- **Manifest.xml** 검색 결과에 포함된 각 항목에 대한 정보가 포함된 매니페스트 파일(XML 형식)입니다. 이 보고서의 정보는 Results.csv 보고서와 같지만 EDRM(전자 검색 참조 모델)에서 지정한 형식입니다. EDRM에 대한 자세한 내용은 로 [https://www.edrm.net](https://www.edrm.net) 이동하세요.
    
 **언제 이러한 보고서를 내보내지 않도록 설정해야 하나요?**
  
특정 요구에 따라 다를 수 있습니다. 많은 조직에서는 검색 결과에 대한 추가 정보가 필요하지 않습니다. 이러한 보고서는 필요하지 않습니다.
  
 **어떤 컴퓨터에서 이 작업을 해야 하나요?**
  
 eDiscovery 내보내기 도구를 실행한 로컬 컴퓨터에서 레지스트리 설정을 변경해야 합니다. 
  
 **이 설정을 변경한 후 컴퓨터를 다시 시작해야 합니까?**
  
아니요. 컴퓨터를 다시 시작할 필요는 없습니다. 그러나 eDiscovery 내보내기 도구가 실행 중인 경우 레지스트리 설정을 변경한 후 해당 도구를 닫았다가 다시 시작해야 합니다.
  
 **기존 레지스트리 키가 편집되거나 새 키가 만들어지나요?**
  
이 항목의 절차에서 만든 .reg 파일을 처음 실행할 때 새 레지스트리 키가 만들어집니다. 그런 다음 .reg 편집 파일을 변경하고 다시 실행할 때마다 설정을 편집합니다.
