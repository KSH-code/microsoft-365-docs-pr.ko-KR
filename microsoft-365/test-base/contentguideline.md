---
title: 테스트 패키지 지침
description: 테스트 패키지에 대한 지침 검토
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 156122ad2b5d92a4a093e92c64b55219238c8ee0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211780"
---
# <a name="test-package-guidelines"></a>테스트 패키지 지침

## <a name="1-script-referencing"></a>1. 스크립트 참조

포털에 .zip 파일을 업로드할 때 해당 파일의 모든 콘텐츠의zip을 루트 폴더로 제거합니다. 이 초기의 unzip 작업을 수행하기 위해 코드를 작성할 필요는 없습니다. 업로드된 zip 파일을 .zip 경로를 사용하여 파일 내의 모든 파일을 참조할 수도 있습니다.

아래 예제에서는 작업 탭의 입력 필드에서 이진/스크립트를 참조하는 방법을 보여 주겠습니다. 텍스트는 인용 부호 없이 **스크립트** 경로 필드에 파란색으로 **입력해야 합니다.**

파일을 업로드하기 전에 zip 파일 내의 콘텐츠를 알고 있어야 합니다. 폴더를 압축할 때 로컬 컴퓨터는 zip 파일 아래에 주 폴더를 만드는 경우가 종종 있습니다. 이 경우 참조는 아래 굵게 **표시됩니다.**

**Contoso_App_Folder.zip**:

```console
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│      ├── file3.exe

│      ├── script.ps1
```

- ScriptX.ps1 - **"Contoso_App_Folder/ScriptX.ps1"**
- Script.ps1 - **"Contoso_App_Folder/folder1/script.ps1"**

다른 경우 zip 파일에 파일 또는 콘텐츠가 바로 아래에 있을 수 있습니다(예: 2nd 수준 폴더 없음).

**Zip_file_uploaded.zip**:

```console
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
```

- ScriptX.ps1 - **"ScriptX.ps1"**
- Script.ps1 - **"folder1/script.ps1"**

## <a name="2-script-execution"></a>2. 스크립트 실행

**Out-of-Box 테스트:** 응용 프로그램 패키지에는 PowerShell 스크립트가 세 개 이상 포함되어야 합니다. 이러한 스크립트는 응용 프로그램 및 해당 종속성의 무인 설치, 시작 및 닫기 작업을 실행합니다. 각 스크립트는 자체 필수조성 확인, 자체 성공의 유효성 검사 및 자체 후 정리(필요한 경우)를 처리해야 합니다.

**기능 테스트:** 응용 프로그램 패키지에는 하나 이상의 PowerShell 스크립트가 포함되어야 합니다. 두 개 이상의 스크립트가 제공되는 경우 스크립트는 업로드 시퀀스에서 실행되고 특정 스크립트의 오류는 후속 스크립트의 실행을 중지합니다.

### <a name="script-requirements"></a>스크립트 요구 사항

- PowerShell 버전 5.1+
- 무인 실행
- 오류 반환 코드
- 성공 확인
- 특정 로그 폴더를 스크립트로 로깅

각 스크립트는 테스트 파이프라인에서 성공적으로 실행하기 위해 무인(사용자 프롬프트 없음)을 실행해야 합니다.

> [!NOTE]
> 스크립트가 성공적으로 완료될 때 "0"을 반환하고 실행 중에 오류가 발생하면 0이 아닌 오류 코드를 반환해야 합니다.

각 스크립트는 성공적으로 실행된지 유효성을 검사해야 합니다. 예를 들어 설치 스크립트는 설치 관리자 이진 실행이 완료된 후 시스템에 특정 바이너리 및/또는 레지스트리 키가 존재하는지 검사해야 합니다. 이 검사는 설치에 성공했다는 적절한 수준의 신뢰를 보장하는 데 도움이 됩니다.

테스트 실행 중에 오류가 발생하는 위치를 제대로 진단하려면 유효성 검사가 필요합니다. 예를 들어 스크립트에서 응용 프로그램을 설치할 수 없거나 응용 프로그램을 설치할 수 없는 경우를 예로 들 수 있습니다.

> [!IMPORTANT]
> **다음을 방지합니다.** 스크립트를 다시 시작해야 하는 경우 스크립트를 업로드하는 동안 다시 시작해야 하는 경우 스크립트를 다시 시작하면 안 됩니다.

## <a name="3-log-collection"></a>3. 로그 컬렉션

각 스크립트는 이라는 폴더에 생성되는 모든 로그를 출력해야 `logs` 합니다. 이름이 인 디렉터리의 모든 폴더가 복사된 후 `logs` 페이지에서 다운로드할 수 `Test Results` 있습니다.

예를 들어 설치 **스크립트(App/scripts/install** 디렉터리에 위치할 수 있습니다.)는 로그를 **로그/install.log에** 출력할 수 있습니다. 즉, 최종 로그가 에 위치하도록 합니다. **Apps/scripts/install/logs/install.log**

시스템은 다른 폴더 내의 다른 파일과 함께 파일을 선택하고 `install.log` `logs` 다운로드를 위해 데이터를 복사합니다.

## <a name="4-application-binaries"></a>4. 응용 프로그램 이진

모든 이진 파일 및 종속성은 단일 zip 파일에 포함해야 합니다.

이러한 이진에는 응용 프로그램 설치에 필요한 모든 것을 포함해야 합니다(예: 응용 프로그램 설치 관리자). 응용 프로그램이 .NET Core/Standard 또는 .NET Framework 프레임워크에 종속된 경우 이러한 프레임워크를 파일에 포함해야 하며 제공된 스크립트에서 올바르게 참조해야 합니다.

> [!NOTE]
> 업로드한 zip 파일에 이름에 공백이나 특수 문자를 사용할 수 없습니다.

## <a name="next-steps"></a>다음 단계

FAQ(질문과 대답)를 보기 위해 다음 **문서로 진행합니다.**
> [!div class="nextstepaction"]
> [다음 단계](faq.md)
