---
title: Microsoft 제품이 아닌 365 데이터를 증거에 로드
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
description: Office 이외 365 콘텐츠 가져오기 기능을 사용 하 여 Office 이외 365 문서를 데이터 조사의 증거에 업로드 하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 499b1074b9a1e2026804eab2ac958fe7392e98ea
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034416"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a>Microsoft 제품이 아닌 365 데이터를 증거에 로드

데이터 조사에서 분석을 수행 하는 데 필요한 모든 문서는 Microsoft 365에 있습니다. 비 Microsoft 365 콘텐츠 가져오기 기능을 사용 하 여 Microsoft 365에 없는 문서를 데이터 조사에서 분석할 수 있도록 증거에 업로드할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

이 절차에 설명 된 것 처럼 365 Microsoft 제품이 아닌 업로드 기능을 사용 하려면 다음이 필요 합니다.

- Microsoft 365 또는 Office 365 E5 구독

- 비 Microsoft 365 콘텐츠가 업로드 될 모든 사용자에 게는 해당 E5 또는 E5 추가 기능 라이선스가 있어야 합니다.

- 기존 eDiscovery 사례

- 업로드 하기 위한 모든 파일은 custodian 당 하나의 폴더가 있고 폴더 이름이이 형식 *alias@domainname*으로 저장 됩니다. *Alias@domainname* 사용자의 별칭 및 도메인 이어야 합니다. 모든 *alias@domainname* 폴더를 루트 폴더로 수집할 수 있습니다. 루트 폴더에는 *alias@domainname* 폴더만 포함할 수 있으며 루트 폴더에는 느슨한 파일이 없어야 합니다.

- 비 Microsoft 365 콘텐츠 폴더 구조에 대 한 액세스 권한이 있는 컴퓨터에 eDiscovery 관리자 또는 eDiscovery 관리자 Microsoft Azure Storage Tools가 설치 되어 있는 계정입니다.

- 다음에서 수행할 수 있는 AzCopy을 설치 합니다.https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a>Microsoft 제품이 아닌 365 콘텐츠를 데이터 조사에 업로드

1. **데이터 조사** 를 열고 Microsoft 제품이 아닌 365 데이터를 업로드할 조사로 이동 합니다.  **증거** 탭을 클릭 한 다음 데이터를 로드할 증거 세트를 선택 합니다.  증명 정보 집합을 아직 만들지 않은 경우 지금 수행할 수 있습니다.  마지막으로 **증거 관리** 를 클릭 하 고 데이터 섹션에서 **업로드를 확인** 합니다.

2. **파일 업로드** 단추를 클릭 하 여 Microsoft 제품이 아닌 365 데이터 가져오기 마법사를 시작 합니다.

![파일 업로드](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 마법사의 첫 번째 단계에서는 업로드할 파일에 대 한 안전한 Azure blob만 준비 합니다.  준비가 완료 되 면 **다음: 파일 업로드** 단추를 클릭 합니다.

![비 Microsoft 365 데이터 가져오기 준비](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. **파일 업로드** 단계에서 **파일의 위치에 대 한 경로**를 지정 합니다. 여기서는 가져오기에 사용할 Microsoft 365이 아닌 데이터를 찾습니다.  올바른 위치를 설정 하면 AzCopy 명령이 제대로 업데이트 됩니다.

> [!NOTE]
> AzCopy을 아직 설치 하지 않은 경우 여기에서이 작업을 수행할 수 있습니다.https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. **클립보드에 복사** 링크를 클릭 하 여 미리 정의 된 명령을 복사 합니다. Windows 명령 프롬프트를 시작 하 고 명령을 붙여 넣은 다음 enter 키를 누릅니다.  파일이 보안 Azure blob 저장소에 업로드 되 고 다음 단계를 진행 합니다.

![비 Microsoft 365 데이터 가져오기를 위한 파일 업로드](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![AzCopy을 사용 하 여 Microsoft 제품이 아닌 365 데이터 가져오기](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 마지막으로 보안 & 준수로 돌아간 **다음: 프로세스 파일** 단추를 클릭 합니다.  이렇게 하면 업로드 된 파일의 처리, 텍스트 추출 및 인덱싱이 시작 됩니다.  여기에서 처리의 진행 상황과 **작업** 탭을 추적할 수 있습니다.  완료 되 면 새 파일을 증거 집합에서 사용할 수 있습니다.  처리가 완료 되 면 마법사를 해제할 수 있습니다.

![타사 365 가져오기 프로세스 파일](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

