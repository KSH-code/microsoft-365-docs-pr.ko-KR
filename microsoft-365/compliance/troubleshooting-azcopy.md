---
title: Advanced eDiscovery에서 AzCopy 문제 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 7a012ec742d99a5b2ba35800c90e8614b503b93c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597325"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Advanced eDiscovery에서 AzCopy 문제 해결

고급 eDiscovery에서 오류 수정을 위해 Office가 아닌 365 데이터 또는 문서를 로드할 때 사용자 인터페이스는 업로드 하려는 파일이 저장 되는 위치 및 Azure 저장소에 있는 매개 변수를 포함 하는 Azure AzCopy 명령을 제공 합니다. 파일이 업로드 될 위치입니다. 문서를 업로드 하려면 로컬 컴퓨터의 명령 프롬프트에서이 명령을 복사한 다음 실행 합니다.  다음 스크린샷에는 AzCopy 명령의 예가 나와 있습니다.

![Office 이외의 365 파일 업로드](media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

일반적으로 제공 되는 명령은 실행할 때 작동 합니다. 그러나 표시 된 명령이 정상적으로 실행 되지 않는 경우가 있을 수 있습니다. 몇 가지 가능한 이유는 다음과 같습니다.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>지원 되는 AzCopy 버전은 로컬 컴퓨터에 설치 되어 있지 않습니다.

이 경우에는 AzCopy v 8.1을 사용 하 여 고급 eDiscovery에서 비 Office 365 데이터를 로드 해야 합니다. 이전 스크린샷에 표시 된 **파일 업로드** 페이지에 표시 되는 AzCopy 명령은 AzCopy v 8.1을 사용 하지 않는 경우 오류를 반환 합니다. 이 버전을 설치 하려면 [Windows의 AzCopy v 8.1을 사용 하 여 데이터 전송을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)참조 하십시오.

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy가 로컬 컴퓨터에 설치 되어 있지 않거나 기본 위치에 설치 되어 있지 않습니다.

AzCopy가 설치 되어 있지 않거나 기본 설치 위치 (is `%ProgramFiles(x86)%`) 이외의 위치에 설치 되어 있는 경우 AzCopy 명령을 실행 하면 다음 오류 메시지가 표시 될 수 있습니다.

    The system cannot find the path specified.

AzCopy가 로컬 컴퓨터에 설치 되어 있지 않으면 [여기](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)에서 설치할 수 있습니다. 기본 위치에 설치 해야 합니다.

AzCopy가 설치 되어 있지만 기본 위치와 다른 위치에 설치 되어 있는 경우 명령을 복사 하 여 텍스트 파일에 붙여 넣은 다음 AzCopy가 설치 된 위치에 대 한 경로를 변경할 수 있습니다. 예를 들어 Azcopy가에 `%ProgramFiles%`있는 경우 명령의 첫 번째 부분 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` 을로 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`변경할 수 있습니다. 이 변경 작업을 수행한 후에는 텍스트 파일에서 복사한 다음 명령 프롬프트를 실행 합니다.

> [!TIP]
> 기본 설치 위치 이외의 위치에 AzCopy가 설치 되어 있으면 제거한 다음 기본 위치에 다시 설치 하는 것이 좋습니다. 이를 통해 나중에이 문제를 방지할 수 있습니다.
