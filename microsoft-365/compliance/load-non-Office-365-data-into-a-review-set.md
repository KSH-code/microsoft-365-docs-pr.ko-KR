---
title: 타사 365 데이터를 검토 집합으로 로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery 사례에서 분석을 위해 365 Microsoft 제품이 아닌 데이터를 검토 집합으로 가져오는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed4a26ea1dd68b9198cce67ce0f97580ed4b2a99
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034426"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>타사 365 데이터를 검토 집합으로 로드

고급 eDiscovery에서 분석 해야 하는 모든 문서는 Microsoft 365에 나와 있습니다. 고급 eDiscovery의 타사 365 데이터 가져오기 기능을 사용 하 여 Microsoft 365에 없는 문서를 검토 집합에 업로드할 수 있습니다. 이 문서에서는 분석을 위해 Microsoft 제품이 아닌 365 문서를 고급 eDiscovery로 가져오는 방법을 설명 합니다.

## <a name="before-you-begin"></a>시작하기 전에

이 문서에서 설명 하는 Microsoft가 아닌 업로드 365 기능을 사용 하려면 다음이 필요 합니다.

- 타사 365 콘텐츠를 연결 하려는 모든 custodians에 해당 하는 라이선스가 할당 되어야 합니다. 자세한 내용은 [Advanced eDiscovery 시작](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)하기를 참조 하세요.

- 기존 고급 eDiscovery 사례

- Microsoft 제품이 아닌 365 데이터를 업로드 하 고 여기에 연결 하려면 Custodians를 사례에 추가 해야 합니다.

- 타사 365 데이터는 고급 eDiscovery에서 지 원하는 파일 형식 이어야 합니다. 자세한 내용은 [Advanced eDiscovery에서 지원 되는 파일 형식을](supported-filetypes-ediscovery20.md)참조 하세요.

- 검토 집합에 업로드 되는 모든 파일은 각 폴더가 특정 custodian 연결 되는 폴더에 있어야 합니다. 이러한 폴더의 이름은 *alias@domainname*다음 명명 형식을 사용 해야 합니다. Alias@domainname 사용자의 Microsoft 365 별칭과 domain 이어야 합니다. 루트 폴더의 모든 alias@domainname 폴더를 수집할 수 있습니다. 루트 폴더에는 alias@domainname 폴더만 포함 될 수 있습니다. 루트 폴더의 느슨한 파일은 지원 되지 않습니다.

   업로드할 비 Microsoft 365 데이터에 대 한 폴더 구조는 다음 예와 비슷합니다.

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   여기서 abraham.mcmahon@contoso.com, jewell.gordon@contoso.com 및 staci.gonzalez@contoso.com는 대/소문자에서 custodians의 SMTP 주소입니다.

   ![타사 365 데이터 업로드 폴더 구조](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- EDiscovery 관리자 역할 그룹에 할당 되 고 eDiscovery 관리자로 추가 된 계정입니다.

- Microsoft 제품이 아닌 365 콘텐츠 폴더 구조에 대 한 액세스 권한이 있는 컴퓨터에 설치 된 AzCopy v 8.1 도구입니다. AzCopy을 설치 하려면 [Windows의 AzCopy v 8.1을 사용 하 여 데이터 전송을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)참조 하세요. 기본 위치인 **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**에 AzCopy을 (를) 설치 해야 합니다. AzCopy v 8.1을 사용 해야 합니다. 고급 eDiscovery에서 Microsoft가 아닌 365 데이터를 로드할 때 다른 버전의 AzCopy 작동 하지 않을 수 있습니다.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>타사 365 콘텐츠를 고급 eDiscovery에 업로드

1. EDiscovery 관리자 또는 eDiscovery 관리자로 이동 하 여 고급 eDiscovery를 열고 365 Microsoft 제품이 아닌 데이터를 업로드 해야 하는 경우를 대비해 야 합니다.  

2. **검토 집합**을 클릭 하 고 검토 집합을 선택 하 여 Microsoft 제품이 아닌 365 데이터를 업로드 합니다.  검토 집합이 없는 경우에는 해당 집합을 만들 수 있습니다. 
 
3. 검토 집합에서 **검토 설정 관리**를 클릭 한 다음 **비 Microsoft 365 데이터** 타일에서 **업로드 보기** 를 클릭 합니다.

4. **파일 업로드** 를 클릭 하 여 데이터 가져오기 마법사를 시작 합니다.

   ![파일 업로드](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   마법사의 첫 번째 단계에서는 Microsoft에서 제공한 안전한 Azure 저장소 위치를 준비 하 여 파일을 업로드 합니다.  준비가 완료 되 면 **다음: 파일 업로드** 단추가 활성화 됩니다.

   ![타사 365 가져오기: 준비](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. **다음: 파일 업로드**를 클릭 합니다.

6. **파일 업로드** 페이지에서 다음을 수행 합니다.

   ![타사 365 가져오기: 파일 업로드](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. **파일 위치 경로** 상자에서 업로드 하려는 타사 365 데이터를 저장 한 루트 폴더의 위치를 확인 하거나 입력 합니다. 예를 들어 **시작 하기 전에 구역**에 표시 된 예제 파일의 위치에는 **%USERPROFILE\Downloads\nonO365**를 입력 합니다. 올바른 위치를 제공 하면 경로 아래의 상자에 표시 되는 AzCopy 명령이 제대로 업데이트 됩니다.

   b. 상자에 표시 된 명령을 복사 하려면 **클립보드에 복사** 를 클릭 합니다.

7. Windows 명령 프롬프트를 시작 하 고 이전 단계에서 복사한 명령을 붙여 넣은 다음 **enter 키를** 눌러 AzCopy 명령을 시작 합니다.  명령을 시작한 후에는 타사 365 파일이 4 단계에서 준비 된 Azure 저장 위치로 업로드 됩니다.

   ![타사 365 가져오기: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 앞에서 설명한 것 처럼 AzCopy v 8.1을 사용 하 여 **파일 업로드** 페이지에 제공 된 명령을 성공적으로 사용 해야 합니다. 제공 된 AzCopy 명령이 실패 하면 [Advanced eDiscovery에서 AzCopy 문제 해결](troubleshooting-azcopy.md)을 참조 하세요.

8. 보안 & 준수 센터로 돌아간 후 **다음: 마법사에서 프로세스 파일** 을 클릭 합니다.  이렇게 하면 Azure 저장소 위치로 업로드 된 비 Microsoft 365 파일의 처리, 텍스트 추출 및 인덱싱이 시작 됩니다.  

9. **검토 집합에 타사 365 데이터를 추가**하는 작업을 보고 **프로세스 파일** 페이지 또는 **작업** 탭에서 파일 처리 진행률을 추적 합니다.  작업이 완료 되 면 검토 집합에서 새 파일을 사용할 수 있습니다.

   ![타사 365 가져오기: 프로세스 파일](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 처리가 완료 되 면 마법사를 닫을 수 있습니다.
