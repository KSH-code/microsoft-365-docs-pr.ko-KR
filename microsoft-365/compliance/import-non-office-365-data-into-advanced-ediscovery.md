---
title: Advanced eDiscovery 분석을 위해 Microsoft가 아닌 365 콘텐츠 가져오기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: AeD로 분석할 수 있도록 Microsoft 365에 저장되지 않은 콘텐츠를 Azure Blob으로 가져오는 단계
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662903"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Advanced eDiscovery(클래식) 분석을 위한 비 Microsoft 365 콘텐츠 가져오기

Advanced eDiscovery를 사용하여 분석해야 할 수 있는 모든 문서가 Microsoft 365에 있는 것은 아니며, Advanced eDiscovery의 비 Microsoft 365 콘텐츠 가져오기 기능을 사용하면 Microsoft 365에 없는 문서(PST 파일 제외)를 사례 연결 Azure 저장소 Blob에 업로드하고 Advanced eDiscovery를 사용하여 분석할 수 있습니다. 이 절차에서는 분석을 위해 Microsoft 365가 아닌 문서를 Advanced eDiscovery로 가져오는 방법을 보여줍니다.
  
> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
> [!NOTE]
> Microsoft 365가 아닌 콘텐츠에 대한 Advanced eDiscovery 데이터 저장소 추가 기능 구독을 구입할 수 있습니다. Advanced eDiscovery를 사용하여 분석할 콘텐츠에 대해 단독으로 사용할 수 있습니다. 비즈니스용 [Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 추가 기능 구입 또는 편집 단계에 따라 Advanced eDiscovery 저장소 추가 기능을 구입합니다. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>비 Office 365 콘텐츠를 업로드하기 위해 요구 사항

이 절차에 설명된 바와 같이 비 Office 365 업로드 기능을 사용하려면 다음을 요구합니다.
  
- 고급 준수 추가 기능 또는 E5 구독이 있는 Office 365 E3
    
- Office 365가 아닌 콘텐츠를 업로드할 모든 관리인은 고급 준수 추가 기능 또는 E5 라이선스가 있는 E3가 있어야 합니다.
    
- 기존 eDiscovery 사례입니다.
    
- 양도자당 폴더가 하나씩 있으며 폴더 이름이 다음 형식인 폴더에 수집된 모든 *alias@domainname.* 이  *alias@domainname*  Office 365 별칭 및 도메인을 지정해야 합니다. 모든 alias@domainname 폴더를 루트 폴더로 수집할 수 있습니다.  루트 폴더는 루트  폴더만 alias@domainname 수 있습니다. 루트 폴더에는 느슨한 파일이 있어야 합니다.
    
- eDiscovery 관리자 또는 eDiscovery 관리자인 계정입니다.
    
- [Office](https://aka.ms/downloadazcopy) 365가 아닌 콘텐츠 폴더 구조에 액세스할 수 있는 컴퓨터에 설치된 Microsoft Azure Storage Tools입니다. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Advanced eDiscovery에 비 Office 365 콘텐츠 업로드


1. eDiscovery 관리자 또는 eDiscovery 관리자로서 **eDiscovery를** 열고 Office 365가 아닌 데이터가 업로드되는 사례를 여는 것입니다. 사례를 만들어야 하는 경우 보안 준수 센터에서 [eDiscovery 사례 &amp; 관리를 참조합니다.](ediscovery-cases.md)
    
2. Advanced **eDiscovery로 전환을 클릭합니다.**

3. 메뉴에서 **검토 집합을** 선택합니다.

4. 기존 검토 집합을 선택하거나 검토 집합 **추가를 선택합니다.**

5. 검토 **집합 관리 선택.**

6. 비 Office 365 데이터 카드에서 업로드 **보기를 선택합니다.**

7. 파일 **업로드 마법사를** 시작하려면 파일 업로드를 선택하십시오.

8. 첫 번째 탭은 **1입니다. 준비 단계.** 다음을 **선택합니다. 파일을 업로드합니다.**

9. **2. 아직 파일을 업로드하지** 않은 경우 AzCopy.exe 다운로드한 다음 파일 위치에 대한 경로를 제공하라는 메시지가 표시됩니다. 예를 들어 명령 실행 명령을 `C:\Upload`  AzCopy.exe. 사용 `C:\Upload` 시 다음이 표시될 것입니다.

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. 명령 프롬프트 창을 열고 AzCopy.exe 명령을 실행하여 데이터를 Azure로 가져올 수 있습니다. 모든 데이터를 로드한 후 **다음: 파일 처리를 선택합니다.**

11. 다음 탭은 **3입니다. 연결된** 데이터가 있는 보호자도 볼 수 있으며 가져오는 데이터의 진행률도 표시하는 파일을 처리합니다.
        
    Azcopy 구문에 대한 자세한 내용은 [Windows에서 AzCopy를](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)사용하여 데이터 전송을 참조하세요. 
    
    Advanced eDiscovery 처리에 대한 자세한 내용은 [Advanced eDiscovery(클래식)에서](run-the-process-module-and-load-data-in-advanced-ediscovery.md)프로세스 모듈 실행 및 데이터 로드를 참조합니다. 
    
    > [!IMPORTANT]
    > 사용자당 하나의 루트 폴더가 있어야 합니다. 폴더 <b>이름은</b>  루트 alias@domainname 형식이 되어야 합니다. 
   
    > [!IMPORTANT]
    > 컨테이너가 Advanced eDiscovery에서 성공적으로 처리된 후 더 이상 Azure의 SAS 저장소에 새 콘텐츠를 추가할 수 없습니다. 추가 콘텐츠를 수집하고 Advanced eDiscovery 분석을 위해 사례에 추가하려면 새 **비 Office 365** 데이터 컨테이너를 만들고 이 절차를 반복해야 합니다. 
  
    > [!NOTE]
    > 폴더  *이름*  문제로 인해 컨테이너가 성공적으로 처리되지 않은 경우 문제를 해결한 경우 이 문서의 절차를 사용하여 새 컨테이너를 만들고 다시 연결한 다음 다시 업로드해야 합니다.
