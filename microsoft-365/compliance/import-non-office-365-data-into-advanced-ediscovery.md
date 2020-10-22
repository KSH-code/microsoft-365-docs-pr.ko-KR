---
title: 고급 eDiscovery 분석을 위해 Microsoft 제품이 아닌 365 콘텐츠 가져오기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: AeD로 분석할 수 있도록 Microsoft 365에 저장 되어 있지 않은 콘텐츠를 Azure blob에 가져오는 방법에 대 한 설명
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636955"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>고급 eDiscovery에 대 한 비 Microsoft 365 콘텐츠 가져오기 (클래식) 분석

고급 eDiscovery를 사용 하 여 분석을 수행 하는 데 필요한 모든 문서는 Microsoft 365에서 살고 있습니다. 고급 eDiscovery의 타사 365 콘텐츠 가져오기 기능을 사용 하 여 PST 파일을 제외한 Microsoft 365에 없는 문서를 연결 된 Azure storage blob에 업로드 하 고 고급 eDiscovery로 분석할 수 있습니다. 이 절차에서는 Microsoft 이외의 365 문서를 분석을 위해 고급 eDiscovery로 가져오는 방법을 설명 합니다.
  
> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
> [!NOTE]
> Microsoft 제품이 아닌 365 콘텐츠에 대 한 고급 eDiscovery 데이터 저장소 추가 기능 구독을 구입할 수 있습니다. 이 기능은 고급 eDiscovery를 사용 하 여 분석 되는 콘텐츠에 대해서만 사용할 수 있습니다. [비즈니스용 Microsoft 365에 대 한 추가 기능 구입 또는 편집](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 의 단계를 따르고, 고급 eDiscovery 저장소 추가 기능을 구입 합니다. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Office 이외의 365 콘텐츠를 업로드 하기 위한 요구 사항

이 절차에 설명 된 대로 Office 이외에 업로드 365 기능을 사용 하려면 다음이 필요 합니다.
  
- 고급 규정 준수 추가 기능 또는 E5 구독을 포함 하는 Office 365 E3
    
- 비 Office 365 콘텐츠가 업로드 되는 모든 custodians에는 고급 규정 준수 추가 기능 또는 E5 라이선스가 포함 된 E3이 있어야 합니다.
    
- 기존 eDiscovery 사례
    
- 업로드 하기 위한 모든 파일은 custodian 당 하나의 폴더가 있고 폴더 이름이이 형식  *alias@domainname*  으로 저장 됩니다. *Alias@domainname* 사용자의 Office 365 별칭과 domain 이어야 합니다. 모든  *alias@domainname*  폴더를 루트 폴더로 수집할 수 있습니다. 루트 폴더에는  *alias@domainname*  폴더만 포함할 수 있으며 루트 폴더에는 느슨한 파일이 없어야 합니다.
    
- EDiscovery 관리자 또는 eDiscovery 관리자 인 계정입니다.
    
- Office가 아닌 365 콘텐츠 폴더 구조에 대 한 액세스 권한이 있는 컴퓨터에 설치 된 [Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) 입니다. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Office 이외의 365 콘텐츠를 고급 eDiscovery에 업로드


1. Ediscovery 관리자 또는 eDiscovery 관리자로 서 **ediscovery**를 열고 비 Office 365 데이터가 업로드 될 사례를 엽니다. 사례를 만들어야 하는 경우 [에는 보안 및 &amp; 준수 센터에서 EDiscovery 사례 관리](ediscovery-cases.md)를 참조 하세요.
    
2. **고급 eDiscovery로 전환을**클릭 합니다.

3. 메뉴에서 **검토 집합** 을 선택 합니다.

4. 기존 검토 집합을 선택 하거나 **검토 설정 추가**를 선택 합니다.

5. **검토 설정 관리**를 선택 합니다.

6. 비 Office 365 데이터 카드에서 **업로드 보기**를 선택 합니다.

7. **업로드 파일** 을 선택 하 여 파일 업로드 마법사를 시작 합니다.

8. 첫 번째 탭은 **1입니다. 준비 단계** **다음: 파일 업로드**를 선택 합니다.

9. **2. 파일 업로드** 탭 아직 완료 하지 않은 경우 AzCopy.exe 다운로드 한 다음 파일 위치에 대 한 경로를 제공 하 라는 메시지가 표시 됩니다. 예를 들어 `C:\Upload`  AzCopy.exe 실행 하는 명령을 제공 합니다. `C:\Upload`를 사용 하면 다음이 표시 됩니다.

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. 명령 프롬프트 창을 열고 AzCopy.exe 명령을 실행 하 여 Azure로 데이터를 가져옵니다. 모든 데이터를 로드 한 후에는 **다음: 프로세스 파일**을 선택 합니다.

11. 다음 탭은 **3입니다. ** 데이터를 포함 하는 custodians를 보게 되는 프로세스 파일과 가져올 데이터의 진행 상황도 표시 됩니다.
        
    Azcopy 구문에 대 한 자세한 내용은 [Transfer data with a Windows Azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)을 참조 하십시오. 
    
    고급 eDiscovery 처리에 대 한 자세한 내용은 [프로세스 모듈 실행 및 고급 ediscovery에서 데이터 로드 (클래식)](run-the-process-module-and-load-data-in-advanced-ediscovery.md)를 참조 하세요. 
    
    > [!IMPORTANT]
    > 사용자 마다 루트 폴더가 하나씩 있어야 하며 폴더 이름은 <b>alias@domainname</b>  형식 이어야 합니다. 
   
    > [!IMPORTANT]
    > 고급 eDiscovery에서 컨테이너를 성공적으로 처리 하면 더 이상 Azure의 SAS 저장소에 새 콘텐츠를 추가할 수 없게 됩니다. 추가 콘텐츠를 수집 하 고 고급 eDiscovery 분석을 위해 사례에 추가 하려는 경우에는 **365 Office가 아닌 새 데이터** 컨테이너를 만들고이 절차를 반복 해야 합니다. 
  
    > [!NOTE]
    > *폴더 명명 문제로 인해 컨테이너가 제대로 처리 되지* 않는 경우 문제를 해결 하는 경우에도이 문서의 절차에 따라 새 컨테이너를 만들고 다시 연결 하 고 업로드 해야 합니다.
