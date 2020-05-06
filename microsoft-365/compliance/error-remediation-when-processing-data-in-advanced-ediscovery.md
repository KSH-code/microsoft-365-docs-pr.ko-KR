---
title: 데이터를 처리할 때 오류 수정
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
description: 오류 수정을 사용 하 여 콘텐츠를 제대로 처리 하지 못할 수 있는 고급 eDiscovery의 데이터 문제를 해결 하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8ada53dd6339541fc39b37903a0f58fd4ad84c8c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035912"
---
# <a name="error-remediation-when-processing-data"></a>데이터를 처리할 때 오류 수정

오류 수정을 통해 eDiscovery 관리자는 고급 eDiscovery가 콘텐츠를 제대로 처리 하지 못하게 하는 데이터 문제를 해결할 수 있습니다. 예를 들어 암호로 보호 된 파일은 파일을 잠그거나 암호화 한 후에 처리할 수 없습니다. 오류 수정을 사용 하는 경우 eDiscovery 관리자는 이러한 오류와 함께 파일을 다운로드 하 고 암호 보호를 제거한 다음 재구성 된 파일을 업로드할 수 있습니다.

다음 워크플로를 사용 하 여 고급 eDiscovery 사례에서 오류가 발생 한 파일을 수정 합니다.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>처리 오류가 있는 파일을 수정 하는 오류 업데이트 관리 세션 만들기

>[!NOTE]
>다음 절차 중에 오류 수정 마법사를 언제 든 지 닫을 경우, **보기** 드롭다운 메뉴에서 **Remediations** 을 선택 하 여 **처리** 탭에서 오류 수정 세션으로 돌아갈 수 있습니다.

1. 고급 eDiscovery 사례의 **처리** 탭에 있는 **보기** 드롭다운 메뉴에서 **오류** 를 선택한 다음 **범위** 드롭다운 메뉴에서 검토 집합 또는 전체 사례를 선택 합니다. 이 섹션에는 특정 검토 집합의 케이스나 오류에 대 한 모든 오류가 표시 됩니다.

   ![오류 수정](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. 오류 유형 또는 파일 형식 옆의 라디오 단추를 클릭 하 여 수정할 오류를 선택 합니다.  다음 예제에서는 암호로 보호 된 파일을 수정 합니다.

3. **새 오류 수정을**클릭 합니다.

    오류 재구성 워크플로는 오류가 발생 한 파일을 Microsoft에서 제공한 Azure 저장소 위치로 복사 하 여 업데이트를 로컬 컴퓨터로 다운로드 하 여 수정할 수 있는 준비 단계로 시작 됩니다.

    ![오류 수정 준비](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 준비가 완료 되 면 **다음: 파일 다운로드** 를 클릭 하 여 다운로드를 계속 합니다.

    ![파일 다운로드](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 파일을 다운로드 하려면 **다운로드 대상 경로**를 지정 합니다. 파일을 다운로드 하는 로컬 컴퓨터의 상위 폴더에 대 한 경로입니다.  기본 경로인%USERPROFILE%\Downloads\errors는 로그인 한 사용자의 다운로드 폴더를 가리킵니다. 원하는 경우이 경로를 변경할 수 있습니다. 이를 변경 하는 경우 최상의 성능을 위해 로컬 파일 경로를 사용 하는 것이 좋습니다. 원격 네트워크 경로를 사용 하지 마십시오. 예를 들어 **C:\remediation**경로를 사용할 수 있습니다. 

   부모 폴더에 대 한 경로는 AzCopy 명령에 자동으로 **/Tdest** 매개 변수 값으로 추가 됩니다.

6. **클립보드에 복사를**클릭 하 여 미리 정의 된 명령을 복사 합니다. Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 **enter 키를**누릅니다.  

    ![오류 수정 준비](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > **파일 다운로드** 페이지에 제공 된 명령을 정상적으로 사용 하려면 AzCopy v 8.1을 사용 해야 합니다. 또한 10 단계에서 AzCopy v 8.1을 사용 하 여 파일을 업로드 해야 합니다. 이 버전의 AzCopy을 설치 하려면 [Windows의 AzCopy v 8.1을 사용 하 여 데이터 전송을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)참조 하세요. 제공 된 AzCopy 명령이 실패 하면 [Advanced eDiscovery에서 AzCopy 문제 해결](troubleshooting-azcopy.md)을 참조 하세요.

    선택한 파일이 5 단계에서 지정한 위치로 다운로드 됩니다. 상위 폴더 (예: **C:\remediation**)에서 다음 하위 폴더 구조가 자동으로 만들어집니다.

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *하위 폴더 1* 은 1 단계에서 선택한 범위에 따라 사례 또는 검토 집합의 ID를 사용 하 여 이름이 지정 됩니다.

    - *하위 폴더 2* 의 이름은 다운로드 한 파일의 파일 ID로 지정 됩니다.

    - 다운로드 된 파일은 *하위 폴더 2* 에 있으며 파일 ID로도 이름이 지정 됩니다.

    다음은 항목을 **C:\remediation** 상위 폴더로 다운로드 했을 때 생성 되는 폴더 경로 및 오류 파일 이름의 예입니다.

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    여러 파일이 다운로드 되는 경우에는 파일 ID로 이름이 지정 된 하위 폴더로 각 파일을 다운로드 합니다.

    > [!IMPORTANT]
    > 9 단계와 10 단계에서 파일을 업로드 하는 경우 재구성 된 파일의 파일 이름이 같고 동일한 하위 폴더 구조에 있어야 합니다. 하위 폴더와 파일 이름은 재구성 된 파일과 원본 오류 파일을 연결 하는 데 사용 됩니다. 폴더 구조 또는 파일 이름이 변경 되 면 다음 오류가 `Cannot apply Error Remediation to the current Workingset`표시 됩니다. 문제를 방지 하려면 재구성 된 파일을 동일한 상위 폴더 및 하위 폴더 구조에 유지 하는 것이 좋습니다.

7. 파일을 다운로드 한 후에는 적절 한 도구를 사용 하 여 수정할 수 있습니다. 암호로 보호 된 파일의 경우에는 여러 가지 암호 해독 도구를 사용할 수 있습니다. 파일에 대 한 암호를 알고 있으면 열고 암호 보호 기능을 제거할 수 있습니다.

8. Advanced eDiscovery 및 오류 수정 마법사로 돌아간 후 **다음: 파일 업로드**를 클릭 합니다.  그러면 파일을 업로드할 수 있는 다음 페이지로 이동 됩니다.

    ![파일 업로드](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. **파일 위치 경로** 텍스트 상자에서 재구성 된 파일이 있는 상위 폴더를 지정 합니다. 마찬가지로 부모 폴더에는 파일을 다운로드할 때 만든 하위 폴더 구조가 있어야 합니다.

    상위 폴더의 경로는 AzCopy 명령 ( **/Source** 매개 변수 값)에 자동으로 추가 됩니다.

10. **클립보드에 복사를**클릭 하 여 미리 정의 된 명령을 복사 합니다. Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 **enter 키를**누릅니다. 파일을 업로드 합니다.

    ![ff2ff691-629f-4065-9b37-5333f937daf6-.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. AzCopy 명령을 실행 한 후에 **다음: 프로세스 파일**을 클릭 합니다.

    처리가 완료 되 면 검토 설정으로 이동 하 여 재구성 한 파일을 볼 수 있습니다. 

## <a name="remediating-errors-in-container-files"></a>컨테이너 파일의 수정 오류

고급 eDiscovery로 컨테이너 파일의 내용 (예: .zip 파일)을 추출할 수 없는 경우 컨테이너를 다운로드 하 고 원래 컨테이너가 있는 동일한 폴더에 콘텐츠를 확장할 수 있습니다. 확장 된 파일은 처음에 고급 eDiscovery로 확장 된 것 처럼 부모 컨테이너에 대 한 특성이 됩니다. 이 프로세스는 한 파일을 대체 파일로 업로드 하는 것을 제외 하 고 위에 설명 된 대로 작동 합니다.  재구성 한 파일을 업로드 하는 경우 원본 컨테이너 파일을 포함 하지 마십시오.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>추출 된 텍스트를 업로드 하 여 오류 수정

고급 eDiscovery에서 해석할 수 있는 기본 형식으로 파일을 수정 하는 것이 불가능할 수도 있습니다. 하지만 원본 파일을 *텍스트 층*이라는 프로세스의 원본 텍스트가 포함 된 텍스트 파일로 바꿀 수 있습니다. 이 작업을 수행 하려면이 문서에서 설명 하는 단계를 수행 하 되, 원본 파일을 기본 형식으로 수정 않고 원본 파일에서 추출한 텍스트를 포함 하는 텍스트 파일을 만든 다음 .txt 접미사로 추가 된 원래 파일 이름을 사용 하 여 텍스트 파일을 업로드 합니다. 예를 들어, 파일 이름 335850cc-6602-4af0-acfa-1d14d9128ca2를 사용 하 여 오류를 수정 하는 중에 파일이 다운로드 됩니다. 네이티브 응용 프로그램에서 파일을 열고 텍스트를 복사한 다음 335850cc-6602-4af0-acfa-1d14d9128ca2 라는 새 파일에 붙여 넣습니다. 이 작업을 수행할 때는 재구성 된 텍스트 파일을 고급 eDiscovery로 업로드 하기 전에 로컬 컴퓨터의 재구성 된 파일 위치에서 원본 파일을 원시 형식으로 제거 해야 합니다.

## <a name="what-happens-when-files-are-remediated"></a>파일을 수정 하는 경우 수행 되는 작업

재구성 한 파일을 업로드 하면 다음 필드를 제외 하 고 원래 메타 데이터가 보존 됩니다. 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 텍스트
- WordCount
- WorkingsetId

Advanced eDiscovery의 모든 메타 데이터 필드에 대 한 정의는 [문서 메타 데이터 필드](document-metadata-fields.md)를 참조 하십시오.
