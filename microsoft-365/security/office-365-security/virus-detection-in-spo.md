---
title: SharePoint Online, OneDrive 및 Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: SharePoint Online에서 사용자가 업로드하는 파일의 바이러스를 감지하고 사용자가 파일을 다운로드하거나 동기화하지 못하게 하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ddb424458e991becefb98efbad5b2a86c5f9441c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208904"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online, OneDrive 및 Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

Microsoft 365 온라인, OneDrive 및 앱에 업로드하는 파일을 검사하는 데 SharePoint 바이러스 검색 엔진을 Microsoft Teams. 이 보호는 SharePoint Online, OneDrive 및 구독을 Microsoft Teams.

> [!IMPORTANT]
> 기본 제공 바이러스 백신 기능은 바이러스를 포함하는 데 도움이 되는 한 가지 방법입니다. 이러한 맬웨어는 사용자 환경에 대한 맬웨어에 대한 단일 방어 지점으로 사용되지 않습니다. 모든 고객은 다양한 계층에서 맬웨어 방지 보호를 조사 및 구현하고 엔터프라이즈 인프라 보안에 대한 모범 사례를 적용하는 것이 좋습니다. 전략 및 모범 사례에 대한 자세한 내용은 [보안 로드맵 을 참조하세요.](security-roadmap.md)

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>감염된 파일이 온라인에 업로드되면 SharePoint 어떻게 하나요?

Microsoft 365 바이러스 검색 엔진은 SharePoint Online 내에서 비동기적으로(파일 업로드와 독립적으로) 실행됩니다. **모든 파일은 자동으로 검색되지 않습니다.** 추론에 따라 검사할 파일이 결정됩니다. 파일이 바이러스를 포함하는 것으로 발견된 경우 파일에 플래그가 지정됩니다. 2018년 4월에는 검사된 파일에 대한 25MB 제한을 제거했습니다.

다음과 같은 상황이 발생합니다.

1. 사용자가 온라인에 파일을 SharePoint 합니다.
2. SharePoint 온라인에서는 바이러스 검사 프로세스의 일부로 나중에 파일이 검사 기준을 충족하는지 여부를 판명합니다.
3. 파일이 검사 기준을 충족하는 경우 바이러스 검색 엔진이 파일을 검색합니다.
4. 검사한 파일에서 바이러스가 발견되면 바이러스 엔진이 파일에 감염되었음을 나타내는 속성을 설정합니다.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>사용자가 브라우저를 사용하여 감염된 파일을 다운로드하면 어떻게 하나요?

파일이 감염된 경우 사용자는 브라우저를 사용하여 SharePoint Online에서 파일을 다운로드할 수 없습니다.

다음과 같은 상황이 발생합니다.

1. 사용자가 웹 브라우저를 열고 온라인에서 감염된 파일을 SharePoint 합니다.
2. 사용자에게 바이러스가 검색된 것 같은 경고가 표시됩니다. 기본적으로 사용자는 파일을 다운로드하고 자체 장치에서 바이러스 백신 소프트웨어를 사용하여 파일을 정리할 수 있는 옵션이 제공됩니다.

> [!NOTE]
>
> 관리자는 SharePoint Online PowerShell의 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet에서 *DisallowInfectedFileDownload* 매개 변수를 사용하여 바이러스 백신 경고 창에서도 사용자가 감염된 파일을 다운로드하지 못하도록 할 수 있습니다. 자세한 내용은 [SharePoint Online PowerShell을](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)사용하여 사용자가 악성 파일을 다운로드하지 못하게 방지를 참조하세요.
>
> *DisallowInfectedFileDownload* 매개 변수를 사용하도록 설정하는 즉시 검색/차단된 파일에 대한 액세스가 사용자 및 관리자에 대해 완전히 차단됩니다.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>클라이언트가 OneDrive 동기화 파일을 동기화하면 어떻게 하나요?

악성 파일이 OneDrive 맬웨어로 표시되기 전에 로컬 컴퓨터와 동기화됩니다. 맬웨어로 표시된 후 사용자는 로컬 컴퓨터의 동기화된 파일을 더 이상 열 수 없습니다.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

Microsoft 365 [Microsoft Defender for](defender-for-office-365.md) Office 365 구독에 포함되거나 추가 기능으로 구매한 조직은 SharePoint, OneDrive 및 Microsoft Teams 보고 및 보호를 위해 금고 첨부 파일을 사용할 수 있습니다. 자세한 내용은 금고, SharePoint 및 OneDrive 첨부 [Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>관련 문서

[맬웨어 및 랜섬웨어 Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

SharePoint Online, OneDrive 및 Microsoft Teams 바이러스 백신에 대한 자세한 내용은 위협으로부터 [](protect-against-threats.md) 보호 및 금고, [SharePoint,](turn-on-mdo-for-spo-odb-and-teams.md)OneDrive 및 Microsoft Teams.
