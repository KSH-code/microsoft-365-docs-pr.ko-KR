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
description: 오류 수정을 사용하여 콘텐츠를 올바르게 처리하지 못하게 할 수 있는 Advanced eDiscovery의 데이터 문제를 수정하는 방법을 알아보겠습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6ef1076e44fca0d060d766fc85a435550c40059
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750801"
---
# <a name="error-remediation-when-processing-data"></a>데이터를 처리할 때 오류 수정

오류 수정을 통해 eDiscovery 관리자는 Advanced eDiscovery가 콘텐츠를 제대로 처리하지 못하게 하는 데이터 문제를 수정하는 기능을 사용할 수 있습니다. 예를 들어 파일이 잠기거나 암호화되어 암호로 보호된 파일은 처리될 수 없습니다. eDiscovery 관리자는 오류 수정을 사용하여 이러한 오류가 있는 파일을 다운로드하고 암호 보호를 제거한 다음 수정된 파일을 업로드할 수 있습니다.

Advanced eDiscovery 사례에서 오류가 있는 파일을 수정하려면 다음 워크플로를 사용하세요.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>오류 처리 오류로 파일을 수정하는 오류 수정 세션 만들기

>[!NOTE]
>다음 절차 중 오류 수정 마법사가 닫히면 보기 드롭다운 메뉴에서 수정을 선택하여 처리 탭에서  오류 수정 세션으로  돌아올 수 있습니다. 

1. Advanced  eDiscovery 사례의 처리 탭에 있는 보기  드롭다운 메뉴에서 오류를 선택한 다음 범위 드롭다운  메뉴에서 검토 집합 또는 전체 사례를 선택합니다.  이 섹션에는 특정 검토 집합의 사례 또는 오류에 대한 모든 오류가 표시됩니다.

   ![오류 수정](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. 오류 유형 또는 파일 형식 옆에 있는 라디오 단추를 클릭하여 수정하려는 오류를 선택합니다.  다음 예제에서는 암호로 보호된 파일을 수정합니다.

3. 새 **오류 수정을 클릭합니다.**

    오류 수정 워크플로는 오류가 있는 파일이 Microsoft에서 제공하는 Azure Storage 위치로 복사되는 준비 단계로 시작하여 수정을 위해 로컬 컴퓨터에 다운로드할 수 있습니다.

    ![오류 수정 준비](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 준비가 완료되면 다음: 파일 **다운로드를** 클릭하여 다운로드를 진행합니다.

    ![파일 다운로드](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 파일을 다운로드하려면 다운로드할 **대상 경로를 지정합니다.** 파일을 다운로드할 로컬 컴퓨터의 상위 폴더 경로입니다.  기본 경로인 %USERPROFILE%\Downloads\errors는 로그인한 사용자의 다운로드 폴더를 지정합니다. 원하는 경우 이 경로를 변경할 수 있습니다. 변경하는 경우 최상의 성능을 위해 로컬 파일 경로를 사용하는 것이 좋습니다. 원격 네트워크 경로를 사용하지 않습니다. 예를 들어 **C:\Remediation** 경로를 사용할 수 있습니다. 

   부모 폴더의 경로는 자동으로 AzCopy 명령에 **추가됩니다(/Dest** 매개 변수의 값).

6. 클립보드에 복사를 클릭하여 미리 정의한 **명령을 복사합니다.** Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 Enter 를 **누르고 있습니다.**  

    ![오류 수정 준비](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > 파일 다운로드 페이지에 제공된 명령을 사용하려면 AzCopy v8.1을 사용하여 성공적으로 **실행해야** 합니다. 또한 AzCopy v8.1을 사용하여 10단계에서 파일을 업로드해야 합니다. 이 버전의 AzCopy를 설치하려면 [Windows에서 AzCopy v8.1을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 전송을 참조합니다. 제공된 AzCopy 명령이 실패하면 [Advanced eDiscovery에서 AzCopy 문제 해결을 참조합니다.](troubleshooting-azcopy.md)

    선택한 파일은 5단계에서 지정한 위치로 다운로드됩니다. 상위 폴더(예: **C:\Remediation)에** 다음과 같은 하위 폴더 구조가 자동으로 만들어집니다.

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *하위 1의* 이름은 1단계에서 선택한 범위에 따라 사례 또는 검토 집합의 ID로 지정됩니다.

    - *하위 파일 2의* 이름이 다운로드한 파일의 파일 ID로 지정됩니다.

    - 다운로드한 파일은 하위 파일 *2에* 있으며 파일 ID로도 이름이 지정됩니다.

    다음은 항목을 **C:\Remediation** 상위 폴더로 다운로드할 때 생성되는 폴더 경로 및 오류 파일 이름의 예입니다.

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    여러 파일이 다운로드되는 경우 각 파일이 파일 ID로 이름이 지정된 하위 폴더로 다운로드됩니다.

    > [!IMPORTANT]
    > 9단계와 10단계에서 파일을 업로드할 때 수정된 파일은 동일한 파일 이름을 들이고 동일한 하위 폴더 구조에 있어야 합니다. 하위 파일 및 파일 이름은 수정된 파일을 원래 오류 파일과 연결하는 데 사용됩니다. 폴더 구조 또는 파일 이름이 변경된 경우 다음 오류가 `Cannot apply Error Remediation to the current Workingset` 표시됩니다. 문제를 방지하려면 수정된 파일을 동일한 상위 폴더 및 하위 폴더 구조에 유지하는 것이 좋습니다.

7. 파일을 다운로드한 후 적절한 도구로 수정할 수 있습니다. 암호로 보호된 파일의 경우 사용할 수 있는 여러 암호 크래킹 도구가 있습니다. 파일의 암호를 알고 있는 경우 파일을 열고 암호 보호를 제거할 수 있습니다.

8. Advanced eDiscovery 및 오류 수정 마법사로 돌아가 **다음: 파일 업로드를 클릭합니다.**  이제 파일을 업로드할 수 있는 다음 페이지로 이동합니다.

    ![파일 업로드](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 수정된 파일이 파일의 경로 텍스트 상자에 **있는** 상위 폴더를 지정합니다. 다시 말하면 상위 폴더는 파일을 다운로드할 때 만들어진 하위 폴더 구조와 동일해야 합니다.

    부모 폴더의 경로는 AzCopy 명령에 **자동으로 추가됩니다(/Source** 매개 변수의 값).

10. 클립보드에 복사를 클릭하여 미리 정의한 **명령을 복사합니다.** Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 Enter 를 **누르고 있습니다.** 파일을 업로드합니다.

    ![Azcopy에서 수정된 파일을 성공적으로 업로드한 결과](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. AzCopy 명령을 실행한 후 **다음: 파일 처리를 클릭합니다.**

    처리가 완료되면 검토 집합으로 이동하여 수정된 파일을 볼 수 있습니다. 

## <a name="remediating-errors-in-container-files"></a>컨테이너 파일의 오류 수정

Advanced eDiscovery에서 컨테이너 파일(예: .zip 파일)의 내용을 추출할 수 없는 경우 컨테이너를 다운로드하고 원본 컨테이너가 있는 폴더로 콘텐츠를 확장할 수 있습니다. 확장된 파일은 원래 Advanced eDiscovery에 의해 확장된 것 같은 부모 컨테이너에 기인합니다. 이 프로세스는 단일 파일을 대체 파일로 업로드하는 경우를 제외하고 위에 설명된 대로 작동합니다.  수정된 파일을 업로드할 때 원본 컨테이너 파일을 포함하지 마십시오.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>추출된 텍스트를 업로드하여 오류 수정

Advanced eDiscovery에서 해석할 수 있는 네이티브 형식으로 파일을 수정하지 않는 경우도 있습니다. 그러나 원본 파일을 텍스트 오버레이라는 프로세스에서 기본 파일의 원본 텍스트가 포함된 텍스트 파일로 바꿀 *수 있습니다.* 이렇게하려면 이 문서에 설명된 단계를 따르지만 원본 파일을 기본 형식으로 수정하는 대신 원본 파일에서 추출된 텍스트가 포함된 텍스트 파일을 만든 다음 .txt 접미사와 함께 추가된 원본 파일 이름을 사용하여 텍스트 파일을 업로드합니다. 예를 들어 파일 이름을 335850cc-6602-4af0-acfa-1d14d9128ca2.abc로 수정하는 동안 파일을 다운로드합니다. 기본 응용 프로그램에서 파일을 열고 텍스트를 복사한 다음 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt. 이렇게 하는 경우 수정된 텍스트 파일을 Advanced eDiscovery에 업로드하기 전에 로컬 컴퓨터의 수정된 파일 위치에서 원본 파일을 기본 형식으로 제거해야 합니다.

## <a name="what-happens-when-files-are-remediated"></a>파일이 수정되는 경우 발생하는 일

수정된 파일이 업로드될 때 다음 필드를 제외한 원래 메타데이터가 보존됩니다. 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 텍스트
- WordCount
- WorkingsetId

Advanced eDiscovery의 모든 메타데이터 필드에 대한 정의는 문서 메타데이터 [필드를 참조합니다.](document-metadata-fields-in-advanced-ediscovery.md)
