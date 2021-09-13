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
description: 오류 수정을 사용하여 콘텐츠의 적절한 처리를 Advanced eDiscovery 데이터 문제를 수정하는 방법을 알아보겠습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4b249f7941d4f366a2651b570286d2974aca176a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184123"
---
# <a name="error-remediation-when-processing-data"></a>데이터를 처리할 때 오류 수정

오류 수정을 통해 eDiscovery 관리자는 콘텐츠가 제대로 처리되지 않도록 하는 데이터 문제를 Advanced eDiscovery 수 있습니다. 예를 들어 암호로 보호된 파일은 잠기거나 암호화된 파일을 처리하지 못합니다. eDiscovery 관리자는 오류 수정을 사용하여 이러한 오류가 있는 파일을 다운로드하고 암호 보호를 제거한 다음 수정된 파일을 업로드할 수 있습니다.

다음 워크플로를 사용하여 오류가 있는 파일을 Advanced eDiscovery 수 있습니다.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>오류 수정 세션을 만들어 처리 오류로 파일을 수정합니다.

> [!NOTE]
> 다음 절차 중에 오류 수정 마법사가 닫히면 보기 드롭다운 메뉴에서 수정을 선택하여 처리 탭에서  오류 수정 세션으로  돌아올 수 있습니다. 

1. Advanced eDiscovery  사례의 처리 탭에서 보기 드롭다운 메뉴에서  오류를 선택한 다음 범위 드롭다운 메뉴에서 검토 집합 또는 전체 사례를 선택합니다.   이 섹션에는 특정 검토 집합의 사례 또는 오류가 모두 표시됩니다.

   ![오류 수정.](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. 오류 유형 또는 파일 형식 옆에 있는 라디오 단추를 클릭하여 수정하려는 오류를 선택합니다.  다음 예제에서는 암호로 보호된 파일을 수정합니다.

3. 새 **오류 수정 을 클릭합니다.**

    오류 수정 워크플로는 오류가 있는 파일을 로컬 컴퓨터에 다운로드하여 수정하기 위해 Microsoft에서 제공하는 Azure Storage 위치에 복사하는 준비 단계로 시작합니다.

    ![오류 수정 준비](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 준비가 완료되면 다음: 파일 **다운로드를** 클릭하여 다운로드를 진행합니다.

    ![파일을 다운로드합니다.](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 파일을 다운로드하려면 **다운로드 대상 경로** 를 지정합니다. 이는 로컬 컴퓨터의 상위 폴더에 대한 경로로, 파일이 이곳으로 다운로드됩니다.  기본 경로인 %USERPROFILE%\Downloads\errors는 로그인한 사용자의 다운로드 폴더를 지정합니다. 원하는 경우 이 경로를 변경할 수 있습니다. 변경하는 경우 최상의 성능을 위해 로컬 파일 경로를 사용하는 것이 좋습니다. 원격 네트워크 경로를 사용하지 않습니다. 예를 들어 **C:\Remediation 경로를 사용할 수 있습니다.**

   부모 폴더의 경로는 자동으로 AzCopy 명령에 **/Dest** 매개 변수 값으로 추가됩니다.

6. **클립보드로 복사** 를 클릭하여 미리 정의된 명령을 복사합니다. 명령 프롬프트를 Windows 열고 AzCopy 명령을 붙여 넣은 다음 **Enter 를 누를 수 있습니다.**

    ![오류 수정을 준비합니다.](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > 파일 다운로드 페이지에 제공된 명령을 사용하려면 AzCopy v8.1을 **사용해야** 합니다. 또한 AzCopy v8.1을 사용하여 10단계에서 파일을 업로드해야 합니다. 이 버전의 AzCopy를 설치하려면 에서 [AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 Windows. 제공된 AzCopy 명령이 실패하면 에서 [AzCopy 문제 해결을 Advanced eDiscovery.](troubleshooting-azcopy.md)

    선택한 파일이 5단계에서 지정한 위치로 다운로드됩니다. 상위 폴더(예: **C:\Remediation**)에 다음 하위 폴더 구조가 자동으로 만들어집니다.

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *Subfolder 1* 은 1단계에서 선택한 범위에 따라 사례 또는 검토 집합의 ID로 이름이 지정됩니다.

    - *Subfolder 2* 는 다운로드한 파일의 파일 ID로 이름이 지정됩니다.

    - 다운로드한 파일은 *Subfolder 2* 에 있으며 파일 ID로 이름이 지정됩니다.

    다음은 항목을 **C:\Remediation** 부모 폴더로 다운로드할 때 생성되는 폴더 경로 및 오류 파일 이름의 예입니다.

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    여러 파일이 다운로드되는 경우 각 파일이 파일 ID로 이름이 지정되는 하위 폴더로 다운로드됩니다.

    > [!IMPORTANT]
    > 9단계와 10단계에서 파일을 업로드할 때 수정된 파일은 동일한 파일 이름을 사용하며 동일한 하위 폴더 구조에 있어야 합니다. 하위 및 파일 이름은 수정된 파일을 원래 오류 파일과 연결하는 데 사용됩니다. 폴더 구조 또는 파일 이름이 변경된 경우 다음 오류가 `Cannot apply Error Remediation to the current Workingset` 발생합니다. . 문제를 방지하려면 수정된 파일을 동일한 상위 폴더 및 하위 폴더 구조에 유지하는 것이 좋습니다.

7. 파일을 다운로드한 후 적절한 도구로 수정할 수 있습니다. 암호로 보호된 파일의 경우 사용할 수 있는 몇 가지 암호 크래킹 도구가 있습니다. 파일의 암호를 알고 있는 경우 파일을 열고 암호 보호를 제거할 수 있습니다.

8. 파일 Advanced eDiscovery 수정 마법사로 돌아가 다음: 파일 업로드 **클릭합니다.**  이렇게 하면 파일을 업로드할 수 있는 다음 페이지로 이동됩니다.

    ![업로드 파일.](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. **파일 위치 경로** 텍스트 상자에서 수정된 파일이 있는 상위 폴더를 지정합니다. 다시 말하면 부모 폴더의 하위 폴더 구조는 파일을 다운로드할 때 만들어진 동일한 하위 폴더 구조가 있어야 합니다.

    부모 폴더의 경로는 자동으로 AzCopy 명령에 /Source 매개 변수 **값으로 추가됩니다.**

10. **클립보드로 복사** 를 클릭하여 미리 정의된 명령을 복사합니다. 명령 프롬프트를 Windows 열고 AzCopy 명령을 붙여 넣은 다음 **Enter 를 누를 수 있습니다.** 파일을 업로드합니다.

    ![Azcopy에서 수정된 파일을 성공적으로 업로드한 결과입니다.](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. AzCopy 명령을 실행한 후 **다음: 파일 처리를 클릭합니다.**

    처리가 완료되면 집합을 검토하여 수정된 파일을 볼 수 있습니다.

## <a name="remediating-errors-in-container-files"></a>컨테이너 파일의 오류 수정

.zip 파일과 같은 컨테이너 파일의 내용을 추출할 수 없는 Advanced eDiscovery 경우 컨테이너를 다운로드할 수 있으며 원본 컨테이너가 있는 동일한 폴더로 콘텐츠를 확장할 수 있습니다. 확장된 파일은 원래 부모 컨테이너에 의해 확장된 Advanced eDiscovery. 이 프로세스는 단일 파일을 대체 파일로 업로드하는 경우를 제외하고 위에 설명된 대로 작동합니다.  수정된 파일을 업로드할 때 원본 컨테이너 파일을 포함하지 마십시오.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>추출된 텍스트를 업로드하여 오류 수정

경우에 따라 파일을 해석할 수 있는 기본 형식으로 파일을 Advanced eDiscovery 없습니다. 그러나 원본 파일을 기본 파일의 원본 텍스트(텍스트 오버레이라고 하는 프로세스)가 포함된 텍스트 파일로 *바꿀 수 있습니다.* 이렇게하려면 이 문서에 설명된 단계를 따르지만 원본 파일을 기본 형식으로 수정하는 대신 원본 파일에서 추출된 텍스트가 포함된 텍스트 파일을 만든 다음 원본 접미사와 함께 추가된 원본 파일 이름을 사용하여 텍스트 파일을 .txt 합니다. 예를 들어 파일 이름 335850cc-6602-4af0-acfa-1d14d9128ca2.abc를 통해 오류를 수정하는 동안 파일을 다운로드할 수 있습니다. 기본 응용 프로그램에서 파일을 열고 텍스트를 복사한 다음 이름이 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt. 이렇게 하는 경우 수정된 텍스트 파일을 로컬 컴퓨터의 수정된 파일 위치에서 기본 형식으로 제거한 후 수정된 텍스트 파일을 Advanced eDiscovery.

## <a name="what-happens-when-files-are-remediated"></a>파일이 수정되는 경우 발생하는 일

수정된 파일이 업로드될 때 다음 필드를 제외하고 원래 메타데이터가 보존됩니다.

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 텍스트
- WordCount
- WorkingsetId

모든 메타데이터 필드에 대한 정의는 Advanced eDiscovery 메타데이터 필드 [를 참조합니다.](document-metadata-fields-in-advanced-ediscovery.md)