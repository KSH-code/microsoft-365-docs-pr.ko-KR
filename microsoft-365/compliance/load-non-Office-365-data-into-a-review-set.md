---
title: 검토 집합에 비 Microsoft 365 데이터 로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery 사례에서 Microsoft 365가 아닌 데이터를 분석용 검토 집합으로 가져오는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903504"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>검토 집합에 비 Microsoft 365 데이터 로드

Advanced eDiscovery에서 분석해야 하는 모든 문서가 Microsoft 365에 있는 것은 아니며, Advanced eDiscovery의 비 Microsoft 365 데이터 가져오기 기능을 사용하면 Microsoft 365에 없는 문서를 검토 집합에 업로드할 수 있습니다. 이 문서에서는 분석을 위해 Microsoft 365가 아닌 문서를 Advanced eDiscovery로 가져오는 방법을 보여줍니다.

## <a name="requirements-to-upload-non-office-365-content"></a>비 Office 365 콘텐츠 업로드 요구 사항

이 문서에 설명된 비 Microsoft 365 업로드 기능을 사용하려면 다음이 필요합니다.

- Microsoft 365가 아닌 콘텐츠를 연결하려는 모든 관리인에게 적절한 라이선스가 할당되어야 합니다. 자세한 내용은 [Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)시작을 참조하세요.

- 기존 Advanced eDiscovery 사례입니다.

- Microsoft 365 이 아닌 데이터를 업로드하고 연결하려면 먼저 사례에 추가해야 합니다.

- Microsoft 365가 아닌 데이터는 Advanced eDiscovery에서 지원하는 파일 형식이 되어야 합니다. 자세한 내용은 [Advanced eDiscovery에서 지원되는 파일 형식을 참조하세요.](supported-filetypes-ediscovery20.md)

- 검토 집합에 업로드되는 모든 파일은 폴더에 있어야 합니다. 폴더에서 각 폴더는 특정 수장과 연결됩니다. 이러한 폴더의 이름은 다음 명명 *형식을 alias@domainname.* 이 alias@domainname Microsoft 365 별칭 및 도메인을 지정해야 합니다. 루트 폴더의 모든 alias@domainname 수집할 수 있습니다. 루트 폴더에는 여러 폴더만 alias@domainname 있습니다. 루트 폴더의 느슨한 파일은 지원되지 않습니다.

   업로드할 Microsoft 365가 아닌 데이터의 폴더 구조는 다음 예제와 유사합니다.

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   여기서 abraham.mcmahon@contoso.com, jewell.gordon@contoso.com 및 staci.gonzalez@contoso.com 은(는) 거래자에 대한 SMTP 주소입니다.

   ![비 Microsoft 365 데이터 업로드 폴더 구조](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- eDiscovery 관리자 역할 그룹에 할당되어 eDiscovery 관리자로 추가된 계정입니다.

- Microsoft 365가 아닌 콘텐츠 폴더 구조에 액세스할 수 있는 컴퓨터에 설치된 AzCopy v8.1 도구입니다. AzCopy를 설치하려면 [Windows에서 AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 전송을 참조합니다. **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy 인 기본 위치에 AzCopy를 설치해야 합니다.** AzCopy v8.1을 사용해야 합니다. Advanced eDiscovery에서 Microsoft 365가 아닌 데이터를 로드할 때 다른 버전의 AzCopy가 작동하지 않을 수 있습니다.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Advanced eDiscovery에 Microsoft 365가 아닌 콘텐츠 업로드

1. eDiscovery 관리자 또는 eDiscovery 관리자로서 Advanced eDiscovery를 열고 비 Microsoft 365 데이터가 업로드되는 경우로 이동하십시오.  

2. 검토 **집합 을** 클릭한 다음 검토 집합을 선택하여 비 Microsoft 365 데이터를 업로드합니다.  검토 집합이 없는 경우 만들 수 있습니다. 
 
3. 검토 집합에서 검토 집합 관리를 **클릭한** 다음 비 **Microsoft 365** 데이터 타일에서 업로드 보기를 클릭합니다. 

4. 파일 **업로드를 클릭하여** 데이터 가져오기 마법사를 시작할 수 있습니다.

   ![파일 업로드](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   마법사의 첫 번째 단계에서는 파일을 업로드할 보안 Microsoft 제공 Azure Storage 위치를 준비합니다.  준비가 완료되면 **다음:** 파일 업로드 단추가 활성화됩니다.

   ![비 Microsoft 365 가져오기: 준비](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. 다음: **파일 업로드를 클릭합니다.**

6. 파일 **업로드 페이지에서** 다음을 클릭합니다.

   ![비 Microsoft 365 가져오기: 파일 업로드](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. 파일의 **위치 경로** 상자에서 업로드할 Microsoft 365가 아닌 다른 데이터를 저장한 루트 폴더의 위치를 확인하거나 입력합니다. 예를 들어 시작하기 전에 섹션에 표시된 예제 파일의 위치에 대해 **%USERPROFILE\Downloads\nonO365** 를 입력합니다. 올바른 위치를 제공하면 경로 아래에 표시된 AzCopy 명령이 올바르게 업데이트됩니다.

   b. **클립보드에 복사를 클릭하여** 상자에 표시되는 명령을 복사합니다.

7. Windows 명령 프롬프트를 시작하고 이전 단계에서 복사한 명령을 붙여 넣은 다음 **Enter를** 눌러 AzCopy 명령을 시작합니다.  명령을 시작하면 Microsoft 365가 아닌 파일이 4단계에서 준비된 Azure Storage 위치에 업로드됩니다.

   ![비 Microsoft 365 가져오기: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 앞서 설명한 것 처럼 파일 업로드 페이지에 제공된 명령을 성공적으로 사용하려면 AzCopy v8.1을 **사용해야** 합니다. 제공된 AzCopy 명령이 실패하면 [Advanced eDiscovery에서 AzCopy 문제 해결을 참조하시기 바랍니다.](troubleshooting-azcopy.md)

8. 보안 및 준수 센터로 & **다음: 마법사에서** 파일 처리를 클릭합니다.  그러면 Azure Storage 위치에 업로드된 비 Microsoft 365 파일의 처리, 텍스트 추출 및 인덱싱이 시작됩니다.  

9. 검토 집합에 비 Microsoft  365 데이터  추가라는 작업을 확인하여 파일 처리 페이지 또는 작업 탭에서 파일 **처리 진행률을 추적합니다.**  작업이 완료되면 검토 집합에서 새 파일을 사용할 수 있습니다.

   ![비 Microsoft 365 가져오기: 파일 처리](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 처리가 완료되면 마법사를 닫을 수 있습니다.