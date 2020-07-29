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
description: Advanced eDiscovery에서 오류 수정을 위해 비 Office 365 데이터를 로드할 때 Azure AzCopy의 오류를 해결 합니다.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: caec3011c89e027f1b78991a3dad842ff4b8c8aa
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434281"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Advanced eDiscovery에서 AzCopy 문제 해결

고급 eDiscovery에서 오류 수정을 위해 Microsoft가 아닌 365 데이터 또는 문서를 로드할 때 사용자 인터페이스는 업로드 하려는 파일이 저장 되는 위치 및 파일이 업로드 될 Azure 저장 위치와 함께 매개 변수가 포함 된 Azure AzCopy 명령을 제공 합니다. 문서를 업로드 하려면 로컬 컴퓨터의 명령 프롬프트에서이 명령을 복사한 다음 실행 합니다.  다음 스크린샷에는 AzCopy 명령의 예가 나와 있습니다.

![타사 365 파일 업로드](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

일반적으로 제공 되는 명령은 실행할 때 작동 합니다. 그러나 표시 된 명령이 정상적으로 실행 되지 않는 경우가 있을 수 있습니다. 몇 가지 가능한 이유는 다음과 같습니다.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>지원 되는 AzCopy 버전은 로컬 컴퓨터에 설치 되어 있지 않습니다.

이 경우에는 AzCopy v 8.1을 사용 하 여 고급 eDiscovery에서 Microsoft가 아닌 365 데이터를 로드 해야 합니다. 이전 스크린샷에 표시 된 **파일 업로드** 페이지에 표시 되는 AzCopy 명령은 AzCopy v 8.1을 사용 하지 않는 경우 오류를 반환 합니다. 이 버전을 설치 하려면 [Windows의 AzCopy v 8.1을 사용 하 여 데이터 전송을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)참조 하십시오.

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy가 로컬 컴퓨터에 설치 되어 있지 않거나 기본 위치에 설치 되어 있지 않습니다.

AzCopy가 설치 되어 있지 않거나 기본 설치 위치 (is) 이외의 위치에 설치 되어 있는 경우 `%ProgramFiles(x86)%` AzCopy 명령을 실행 하면 다음 오류 메시지가 표시 될 수 있습니다.

> 시스템이 지정한 경로를 찾을 수 없습니다.

AzCopy가 로컬 컴퓨터에 설치 되어 있지 않은 경우 [Windows의 AzCopy v 8.1을 사용 하 여 전송 데이터](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)에서 설치 정보를 확인할 수 있습니다. 기본 위치에 설치 해야 합니다.

AzCopy가 설치 되어 있지만 기본 위치와 다른 위치에 설치 되어 있는 경우 명령을 복사 하 여 텍스트 파일에 붙여 넣은 다음 AzCopy가 설치 된 위치에 대 한 경로를 변경할 수 있습니다. 예를 들어 Azcopy가에 있는 경우 `%ProgramFiles%` 명령의 첫 번째 부분을로 변경할 수 있습니다 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . 이 변경 작업을 수행한 후에는 텍스트 파일에서 복사한 다음 명령 프롬프트를 실행 합니다.

> [!TIP]
> 기본 설치 위치 이외의 위치에 AzCopy가 설치 되어 있으면 제거한 다음 기본 위치에 다시 설치 하는 것이 좋습니다. 이를 통해 나중에이 문제를 방지할 수 있습니다.
