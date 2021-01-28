---
title: 무제한 보관 개요
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Exchange Online 사서함에 무제한 보관 저장소를 제공하는 자동 확장 보관에 대해 자세히 알아보습니다.
ms.openlocfilehash: 9692ba27c64f41ac584bb4008a8b860daab031f5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029434"
---
# <a name="overview-of-unlimited-archiving"></a>무제한 보관 개요

Office 365에서 보관 사서함은 사용자에게 추가 사서함 저장소 공간을 제공합니다. 사용자의 보관 사서함을 사용하도록 설정하면 최대 100GB의 추가 저장소를 사용할 수 있습니다. 과거에는 100GB 저장소 할당량에 도달할 때 조직에서 보관 사서함에 대한 추가 저장소 공간을 요청하기 위해 Microsoft에 문의해야 합니다. 더 이상 그럴 수가 없는 경우입니다.

Microsoft 365의 무제한 보관 기능(자동 확장 보관이라고도함)은 보관 사서함에 추가 저장소를 제공합니다.  보관 사서함의 저장소 할당량에 도달하면 Microsoft 365에서 자동으로 보관함 크기가 증가합니다. 즉, 사용자는 사서함 저장소 공간을 모두 사용할 수 있으며 관리자가 보관 사서함에 대한 추가 저장소를 요청할 필요는 없습니다.

자동 확장 보관을 켜는 단계별 지침은 무제한 보관 사용을 [참조하세요.](enable-unlimited-archiving.md)

> [!NOTE]
> 자동 확장 보관 기능은 공유 사서함도 지원합니다. 공유 사서함에 대해 보관 사서함을 사용하도록 설정하려면 Exchange Online 계획 2 라이선스 또는 Exchange Online 계획 1 라이선스와 Exchange Online Archiving 라이선스가 필요합니다.

## <a name="how-auto-expanding-archiving-works"></a>자동 확장 보관의 작동 방식

앞서 설명한처럼 사용자의 보관 사서함을 사용하도록 설정하면 추가 사서함 저장소 공간이 만들어집니다. 자동 확장 보관을 사용하도록 설정하면 Microsoft 365는 보관 사서함의 크기를 주기적으로 확인합니다. 보관 사서함이 저장 용량 제한에 가까워지면 Microsoft 365는 보관 사서함에 대한 추가 저장소 공간을 자동으로 만듭니다. 사용자가 이 추가 저장소 공간을 사용할 수 있는 경우 Microsoft 365는 사용자의 보관에 더 많은 저장 공간을 추가합니다. 이 프로세스는 자동으로 수행됩니다. 즉, 관리자가 추가 보관 저장소를 요청하거나 자동 확장 보관을 관리할 필요가 없습니다.

다음은 프로세스에 대한 간략한 개요입니다.

![자동 확장 보관 프로세스 개요](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 사용자 사서함 또는 공유 사서함에 대해 보관을 사용할 수 있습니다. 저장소 공간이 100GB인 보관 사서함이 만들어지며 보관 사서함에 대한 경고 할당량은 90GB로 설정됩니다.

2. 관리자가 사서함에 대해 자동 확장 보관을 사용할 수 있습니다. 복구 가능한 항목 폴더를 포함한 보관 사서함이 90GB에 도달하면 자동 확장 보관함으로 변환되고 Microsoft 365는 보관함에 저장 공간을 추가합니다. 추가 저장소 공간을 프로비전하는 데 최대 30일이 걸릴 수 있습니다.

   > [!NOTE]
   > 사서함이 보류 중이거나 보존 정책에 할당된 경우 자동 확장 보관을 사용하도록 설정하면 보관 사서함의 저장소 할당량은 110GB로 증가합니다. 마찬가지로 보관 경고 할당량도 100GB로 늘어났습니다.

3. Microsoft 365는 필요한 경우 자동으로 더 많은 저장 공간을 추가합니다.

> [!IMPORTANT]
> 자동 확장 보관은 하루당 1GB를 초과하지 않는 증가율의 개별 사용자(또는 공유 사서함)에 사용되는 사서함에만 지원됩니다. 사용자의 보관 사서함은 해당 사용자만을 위한 것입니다. 저널링, 전송 규칙 또는 자동 전달 규칙을 사용하여 메시지를 보관 사서함으로 복사할 수 없습니다. Microsoft는 사용자의 보관 사서함이 다른 사용자의 보관 데이터를 저장하는 데 사용되는 경우 또는 부적절한 사용의 경우 무제한 보관을 거부할 권리가 있습니다.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>추가 보관 저장소 공간으로 이동하는 이유는 무엇입니까?

자동 확장 보관 저장소를 효율적으로 사용하기 위해 폴더가 이동될 수 있습니다. Microsoft 365는 보관에 추가 저장소가 추가될 때 이동되는 폴더를 확인합니다. 폴더를 이동할 때 하나 이상의 하위 폴더가 자동으로 만들어지며 원본 폴더의 항목이 이동 프로세스를 용이하게 하기 위해 이러한 폴더에 배포되는 경우도 있습니다. Outlook에서 폴더 목록의 보관 부분을 볼 때 이러한 하위 폴더는 원래 폴더 아래에 표시됩니다.  Microsoft 365에서 이러한 하위폴더의 이름을 지정하는 데 사용하는 명명 규칙은 **\<folder name\> _yyyy(mmm dd, y** h_mm에서 생성)입니다. 여기서:

- **yyyy는** 폴더의 메시지를 받은 연도입니다.

- **mmm dd, y h_m** 는 사용자의 표준 시간대 및 Outlook의 국가별 설정에 따라 Office 365에서 하위폴더를 만든 날짜 및 시간입니다.

다음 스크린샷은 메시지가 자동 확장 보관함으로 이동되기 전과 후에 폴더 목록을 보여 주며,

 **추가 저장소가 추가되기 전에**

![자동 확장 보관이 프로비전되기 전 보관 사서함의 폴더 목록](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **추가 저장소 추가 후**

![자동 확장 보관이 프로비전된 후 보관 사서함의 폴더 목록](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 앞서 설명한 대로 Microsoft 365는 보조 보관함으로 콘텐츠를 배포할 수 있도록 항목을 하위폴더로 이동하고 위에서 설명한 명명 규칙을 사용하여 이름을 변경합니다. 그러나 항목을 하위폴더로 이동하는 것은 항상 해당되지 않을 수 있습니다. 경우에 따라 전체 폴더가 보조 보관함으로 이동될 수 있습니다. 이 경우 폴더는 원래 이름을 그대로 하게 됩니다.  Outlook의 폴더 목록에서 폴더가 보조 보관함으로 이동된 것이 분명하지는 않습니다.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>자동 확장 보관함의 항목에 액세스하기 위한 Outlook 요구 사항

자동 확장 보관 파일에 저장된 메시지에 액세스하기 위해 사용자는 다음 Outlook 클라이언트 중 하나를 사용해야 합니다.

- Windows용 Outlook 2016 또는 Outlook 2019

- 웹용 Outlook

- Outlook 2016 또는 Outlook 2019 for Mac

다음은 Outlook 또는 웹용 Outlook을 사용하여 자동 확장 보관 파일에 저장된 메시지에 액세스할 때 고려해야 할 몇 가지입니다.

- 자동 확장 저장소 영역으로 이동된 폴더를 포함하여 보관 사서함의 모든 폴더에 액세스할 수 있습니다.

- 자동 확장 보관 검색은 웹용 Outlook에서 사용할 수 있습니다. 온라인 보관과 마찬가지로 현재 폴더 자체만 검색하여 추가 저장 영역으로 이동된 항목을 검색할 수 있습니다. 즉, 폴더 목록에서 보관 폴더를 선택한 다음 단일 폴더를 검색 범위로 선택해야 합니다. 마찬가지로 자동 확장 저장소 영역의 폴더에 하위 폴더가 포함되어 있는 경우 각 하위 폴더를 개별적으로 검색해야 합니다.
- 자동 확장 보관 검색은 현재 채널의 Outlook 데스크톱(미리 보기)에서 사용할 수 있습니다. 이 미리 보기 내에서 현재 사서함 범위를 사용할 수 있어 자동 확장된 보관 사서함을 검색할 수 있습니다. 이 기능과 기타 Microsoft Search 지원 기능에 대한 자세한 내용은 Exchange Online에 연결된 [Windows용 Outlook에서 Microsoft Search를](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)활용하는 방법을 참조하세요. 

- 자동 확장된 보관함의 Outlook 및 읽기/읽지 않은 항목 수(Outlook 및 웹용 Outlook)의 항목 수가 정확하지 않을 수 있습니다.

- 자동 확장 저장소 영역을 지정하는 하위 폴더의 항목을 삭제할 수 있지만 폴더 자체는 삭제할 수 없습니다.

- 지우기 항목 복구 기능을 사용하여 자동 확장된 저장소 영역에서 삭제된 항목을 복구할 수 없습니다.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>자동 확장 보관 및 기타 규정 준수 기능

이 섹션에서는 자동 확장 보관과 기타 규정 준수 및 데이터 거버넌스 기능 간의 기능에 대해 설명합니다.

- **eDiscovery:** 콘텐츠 검색 또는 In-Place eDiscovery와 같은 eDiscovery 도구를 사용하는 경우 자동 확장 보관함의 추가 저장소 영역도 검색됩니다.

- **보존:** Exchange Online의 소송 보존 또는 eDiscovery 사례 보류 및 보안 및 준수 센터의 보존 정책과 같은 도구를 사용하여 사서함을 보류할 경우 자동 확장된 보관함에 있는 콘텐츠도 보류됩니다.

- **MRM(메시징 레코드 관리):** Exchange Online에서 MRM 삭제 정책을 사용하여 만료된 사서함 항목을 영구적으로 삭제하는 경우 자동 확장 보관함에 있는 만료된 항목도 삭제됩니다.

- **가져오기 서비스:** Office 365 가져오기 서비스를 사용하여 PST 파일을 사용자의 자동 확장 보관함으로 가져올 수 있습니다. PST 파일에서 사용자의 보관 사서함으로 최대 100GB의 데이터를 가져올 수 있습니다.

## <a name="more-information"></a>추가 정보

자동 확장 보관에 대한 자세한 기술 정보는 [Microsoft 365:](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)자동 확장 보관함 FAQ를 참조합니다.
