---
title: Microsoft가 아닌 365 데이터를 검토 집합에 로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 비영리 Microsoft 365 분석용 검토 집합으로 가져오는 방법을 Advanced eDiscovery 방법을 참조합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9de9c4044b9c8ba4af5112475e51e517d0c73946
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175146"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Microsoft가 아닌 365 데이터를 검토 집합에 로드

특정 문서에서 분석해야 하는 모든 Advanced eDiscovery 문서가 Microsoft 365. Advanced eDiscovery에서 Microsoft 365 외의 데이터 가져오기 기능을 사용하면 Microsoft 365에 없는 문서를 검토 집합에 업로드할 수 있습니다. 이 문서에서는 비보안 문서를 분석용 문서로 Microsoft 365 방법을 Advanced eDiscovery 보여줍니다.

## <a name="requirements-to-upload-non-office-365-content"></a>비영리 Office 365 업로드하기 위한 요구 사항

이 문서에 Microsoft 365 비영구 업로드 기능을 사용하려면 다음이 필요합니다.

- 비영리 콘텐츠와 연결하려는 모든 Microsoft 365 적절한 라이선스를 할당해야 합니다. 자세한 내용은 에서 [시작을 Advanced eDiscovery.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

- 기존 Advanced eDiscovery 사례입니다.

- 비보안 데이터를 업로드하고 연결하려면 먼저 사례에 추가해야 Microsoft 365 수 있습니다.

- 타사 365 데이터는 Advanced eDiscovery에서 지원되는 파일 형식이어야 합니다. 자세한 내용은 [Advanced eDiscovery에서 지원되는 파일 형식](supported-filetypes-ediscovery20.md)을 참조하세요.

- 검토 세트에 업로드되는 모든 파일은 폴더에 있어야 하며, 각 폴더는 특정 보유자와 연결되어 있어야 합니다. 이러한 폴더의 이름은 *alias@domainname* 과 같은 이름 형식을 사용해야 합니다. 별칭@도메인 이름은 사용자의 Microsoft 365 별칭 및 도메인과 일치해야 합니다. 루트 폴더의 모든 alias@domainname 수집할 수 있습니다. 루트 폴더에는 여러 폴더만 alias@domainname 있습니다. 루트 폴더의 느슨한 파일은 지원되지 않습니다.

   업로드하려는 비 Microsoft 365 폴더 구조는 다음 예제와 유사합니다.

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   여기서 abraham.mcmahon@contoso.com, jewell.gordon@contoso.com 및 staci.gonzalez@contoso.com 은(는) 거래자에 대한 SMTP 주소입니다.

   ![비데이터 Microsoft 365 업로드 폴더 구조입니다.](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- eDiscovery 관리자 역할 그룹에 할당되어 eDiscovery 관리자로 추가된 계정입니다.

- 비영리 콘텐츠 폴더 구조에 액세스할 수 있는 컴퓨터에 설치된 AzCopy v8.1 Microsoft 365 있습니다. AzCopy를 설치하려면 에서 [AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 Windows. **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy 인 기본 위치에 AzCopy를 설치해야 합니다.** AzCopy v8.1을 사용해야 합니다. 다른 버전의 AzCopy는 다른 버전의 AzCopy에서 비영구 데이터를 로드할 Microsoft 365 작동하지 Advanced eDiscovery.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>업로드 콘텐츠를 Microsoft 365 콘텐츠를 Advanced eDiscovery

1. eDiscovery 관리자 또는 eDiscovery 관리자로서 Advanced eDiscovery 열고 비영리 Microsoft 365 업로드하는 경우로 이동하십시오.  

2. 검토 **집합 을** 클릭한 다음 검토 집합을 선택하여 비영구 데이터를 Microsoft 365 클릭합니다.  검토 집합이 없는 경우 만들 수 있습니다. 
 
3. 검토 집합에서 **검토 집합 관리** 를 클릭한 다음 **비 Microsoft 365 데이터** 타일의 **업로드 보기** 를 클릭합니다.

4. **파일 업로드** 를 클릭하여 데이터 가져오기 마법사를 시작합니다.

   ![업로드 파일.](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   마법사의 첫 번째 단계에서는 파일을 업로드할 안전한 Microsoft 제공 Azure Storage 위치를 준비합니다.  준비가 완료되면 **다음: 파일 업로드** 버튼이 활성화됩니다.

   ![비영구 Microsoft 365 가져오기: 준비.](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. **다음: 파일 업로드** 를 클릭합니다.

6. 파일 **업로드 페이지에서** 다음을 합니다.

   ![비영구 Microsoft 365 가져오기: 업로드.](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. 파일 **위치** 경로 상자에서 업로드할 비영구 데이터를 저장한 루트 폴더의 위치를 확인하거나 Microsoft 365 입력합니다. 예를 들어 시작하기 전에 섹션에 표시된 예제 파일의 위치에 대해 **onO365에 %USERPROFILE\Downloads\n입력합니다.** 올바른 위치를 제공하면 경로 아래에 표시된 AzCopy 명령이 올바르게 업데이트됩니다.

   b. **클립보드에 복사를 클릭하여** 상자에 표시되는 명령을 복사합니다.

7. 명령 Windows 시작하고 이전 단계에서 복사한 명령을 붙여 넣은 다음 **Enter를** 눌러 AzCopy 명령을 시작합니다.  명령을 시작하면 비 Microsoft 365 파일이 4단계에서 준비된 Azure Storage 위치로 업로드됩니다.

   ![비영구 Microsoft 365 가져오기: AzCopy.](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 앞서 설명한 것 처럼 AzCopy v8.1을 사용하여 파일 페이지에서 제공된 명령을 업로드 **합니다.** 제공된 AzCopy 명령이 실패하면 에서 [AzCopy 문제 해결을 Advanced eDiscovery.](troubleshooting-azcopy.md)

8. 파일로 Microsoft 365 규정 준수 센터 **다음: 마법사에서** 파일 처리를 클릭합니다.  이렇게 하면 Azure Storage 위치에 업로드된 Microsoft 365가 아닌 파일에 대한 처리, 텍스트 추출 및 인덱싱이 시작됩니다.  

9. 검토 집합에 비영구  데이터 추가라는 작업을  확인하여 파일 처리 페이지 또는 작업 탭에서 Microsoft 365 **진행률을 추적합니다.**  작업이 완료되면 검토 집합에서 새 파일을 사용할 수 있습니다.

   ![비영구 Microsoft 365: 파일 처리.](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 처리가 완료되면 마법사를 닫을 수 있습니다.