---
title: SharePoint Online에서의 바이러스 탐지
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 사용자가 업로드 하 고 사용자가 파일을 다운로드 하거나 동기화 하지 못하게 하는 파일에서 SharePoint Online이 바이러스를 감지 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6bfc23ca4120122ecfa44ad4d39795fed22af84
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429923"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online, OneDrive 및 Microsoft 팀의 바이러스 검색

Microsoft 365는 사용자가 SharePoint Online, OneDrive 및 Microsoft 팀에 업로드 하는 파일에서 바이러스를 검색 하 여 맬웨어 로부터 환경을 보호 하는 데 도움이 될 수 있습니다. 파일을 업로드 한 후 바이러스가 검색 될 수 있습니다. 파일이 감염 된 것으로 확인 되 면 사용자가 파일을 다운로드 하거나 동기화 할 수 없도록 속성이 설정 됩니다.

> [!IMPORTANT]
> SharePoint Online의 이러한 바이러스 백신 기능은 바이러스를 포함 하는 방법입니다. 사용자 환경에 대 한 맬웨어를 방어 하기 위한 단일 방어선이 아닙니다. 모든 고객은 다양 한 계층에서 맬웨어 방지 보호 기능을 평가 및 구현 하 고 엔터프라이즈 인프라를 보호 하기 위한 모범 사례를 적용할 것을 권장 합니다. 전략과 모범 사례에 대 한 자세한 내용은 [보안 로드맵](security-roadmap.md)를 참조 하십시오.

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>감염 된 파일을 SharePoint Online에 업로드 한 경우 어떻게 되나요?

Microsoft 365에서는 일반적인 바이러스 검색 엔진을 사용 합니다. 엔진은 SharePoint Online 내에서 비동기적으로 실행 되며 업로드 후 일부 파일을 검색 합니다. 휴리스틱은 검색할 파일을 결정 하는 데 사용 됩니다. 바이러스를 포함 하는 파일을 찾으면 다시 다운로드할 수 없도록 플래그가 지정 됩니다. 2018 년 4 월에는 검색 된 파일에 대 한 250MB 제한이 제거 되었습니다.

수행 되는 작업은 다음과 같습니다.

1. 사용자가 파일을 SharePoint Online에 업로드 합니다.

2. SharePoint Online은 파일이 검색 조건을 충족 하는지 여부를 확인 합니다.

3. 바이러스 검색 엔진이 파일을 검사 합니다.

4. 바이러스가 발견 되 면 바이러스 엔진은 파일에서 감염 되었음을 나타내는 속성을 설정 합니다.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>사용자가 브라우저를 사용 하 여 감염 된 파일을 다운로드 하려고 하면 어떻게 되나요?

파일이 감염 된 경우 사용자는 브라우저를 사용 하 여 SharePoint Online에서 파일을 다운로드할 수 없습니다.

수행 되는 작업은 다음과 같습니다.

1. 사용자가 웹 브라우저를 열고 SharePoint Online에서 감염 된 파일을 다운로드 하려고 합니다.

2. 사용자에 게 바이러스가 감지 되었음을 알리는 경고가 표시 됩니다. 사용자에 게 파일을 다운로드 하 고 자체 바이러스 백신 소프트웨어를 사용 하 여 복구를 시도할 수 있는 옵션이 제공 됩니다.

> [!NOTE]
> 
> SharePoint Online PowerShell에서 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) Cmdlet의 *DisallowInfectedFileDownload* 매개 변수를 사용 하 여 바이러스 백신 경고 창 에서도 사용자가 감염 된 파일을 다운로드 하지 못하도록 할 수 있습니다.
> 
> 또한 *DisallowInfectedFileDownload* 매개 변수를 사용 하도록 설정 하는 즉시 검색 된/차단 된 파일에 대 한 액세스 권한이 사용자 및 관리자에 대해 완전히 차단 됩니다.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 동기화 클라이언트가 감염 된 파일을 동기화 하려고 할 때 수행 되는 작업

사용자가 새 OneDrive 동기화 클라이언트 (OneDrive.exe) 또는 이전 비즈니스용 OneDrive 동기화 클라이언트 (Groove.exe)를 사용 하 여 파일을 동기화 하는지 여부에 관계 없이 파일에 바이러스가 포함 되어 있으면 동기화 클라이언트에서 다운로드 하지 않습니다. 동기화 클라이언트에서는 파일을 동기화 할 수 없다는 알림을 표시 합니다.

## <a name="extended-capabilities-with-office-365-atp"></a>Office 365 ATP를 사용한 확장 기능

Sharepoint, OneDrive 및 Microsoft 팀에서 Office 365 ATP를 사용 하도록 설정한 고객은 [sharepoint, onedrive](turn-on-atp-for-spo-odb-and-teams.md) 및 microsoft 팀에서 ATP 및 atp 검색을 위해 격리 된 파일을 관리 하기 위해 보안 & 준수 센터를 사용할 수 있습니다. [ATP 전용: 보안 & 준수 센터를 사용 하 여 격리 된 파일을 관리](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)합니다.

## <a name="more-information"></a>추가 정보

SharePoint Online 바이러스 백신을 구성 하는 방법에 대 한 자세한 내용은 [위협 으로부터 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) 하 고 [, sharepoint, OneDrive 및 MICROSOFT 팀에서 ATP를 켜십시오](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) .를 참조 하세요.


