---
title: AzCopy의 문제 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Azure AzCopy에서 오류 수정을 위해 비영구 데이터를 Office 365 Azure AzCopy에 대한 오류를 Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 45f82482f92e740383eca774671f1abd55535675
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174978"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>AzCopy의 문제 Advanced eDiscovery

Advanced eDiscovery 오류 수정을 위해 비영구 데이터 또는 문서를 로드할 때 사용자 인터페이스는 업로드할 파일이 저장되는 위치와 파일이 업로드될 Azure 저장소 위치가 포함된 매개 변수가 포함된 Azure AzCopy 명령을 제공합니다. Microsoft 365 문서를 업로드하려면 이 명령을 복사한 다음 로컬 컴퓨터의 명령 프롬프트에서 실행합니다.  다음 스크린샷은 AzCopy 명령의 예를 보여줍니다.

![업로드 파일을 Microsoft 365 파일입니다.](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

일반적으로 제공된 명령은 실행할 때 작동합니다. 그러나 표시되는 명령이 성공적으로 실행되지 않는 경우도 있습니다. 다음과 같은 몇 가지 이유가 있습니다.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>지원되는 AzCopy 버전이 로컬 컴퓨터에 설치되어 있지 않습니다.

이때 AzCopy v8.1을 사용하여 비영구 데이터를 Microsoft 365 로드해야 Advanced eDiscovery. 이전 스크린샷에 표시된 업로드 파일 페이지에  표시되는 AzCopy 명령은 AzCopy v8.1을 사용하지 않는 경우 오류를 반환합니다. 이 버전을 설치하려면 에서 [AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 Windows.

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy가 로컬 컴퓨터에 설치되지 않은 경우 또는 기본 위치에 설치되지 않습니다.

AzCopy가 설치되지 않은 경우 또는 기본 설치 위치(를) 아닌 다른 위치에 설치하면 AzCopy 명령을 실행할 때 다음 오류가 표시될 `%ProgramFiles(x86)%` 수 있습니다.

> 시스템에서 지정된 경로를 찾을 수 없습니다.

로컬 컴퓨터에 AzCopy가 설치되어 있지 않은 경우 의 [AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 전송에서 설치 정보를 Windows. 기본 위치에 설치해야 합니다.

AzCopy가 설치되지만 기본 위치가 아니라 다른 위치에 설치된 경우 명령을 복사하여 텍스트 파일에 붙여 넣은 다음 AzCopy가 설치된 위치로 경로를 변경할 수 있습니다. 예를 들어 Azcopy가 에 있는 경우 명령의 첫 번째 부분을 에서 로 변경할 `%ProgramFiles%` 수 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 있습니다. 이 변경을 한 후 텍스트 파일에서 복사한 다음 명령 프롬프트를 실행합니다.

> [!TIP]
> AzCopy가 다른 위치에 설치된 경우 기본 설치 위치를 설치한 다음 기본 위치에 다시 설치하는 것이 좋습니다. 이렇게 하면 향후 이 문제를 방지하는 데 도움이 될 수 있습니다.