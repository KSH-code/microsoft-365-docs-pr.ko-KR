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
description: 사서함에 무제한 보관 저장소를 제공하는 자동 확장 보관에 Exchange Online 대해 자세히 알아보습니다.
ms.openlocfilehash: be6fc33879a43d01dfde1312d7144994ff18fd18
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216275"
---
# <a name="overview-of-unlimited-archiving"></a>무제한 보관 개요

이 Office 365 보관 사서함은 사용자에게 추가 사서함 저장소 공간을 제공합니다. 사용자의 보관 사서함을 사용하도록 설정한 후 최대 100GB의 추가 저장소를 사용할 수 있습니다. 과거에는 100GB 저장소 할당량에 도달할 때 조직에서 보관 사서함에 대한 추가 저장소 공간을 요청하기 위해 Microsoft에 문의해야 합니다. 더 이상 그럴 수가 없는 경우

보관 사서함의 무제한 보관 Microsoft 365(자동 확장 보관)는 보관 사서함에 추가 저장소를 제공합니다. 보관 사서함의 저장소 할당량에 도달하면 Microsoft 365 자동으로 보관함 크기가 증가합니다. 즉, 사용자는 사서함 저장소 공간을 모두 사용할 수 있으며 관리자는 보관 사서함에 대한 추가 저장소를 요청할 필요는 없습니다.

자동 확장 보관을 켜는 단계별 지침은 무제한 보관 사용 [을 참조하세요.](enable-unlimited-archiving.md)

> [!NOTE]
> 자동 확장 보관 기능은 공유 사서함도 지원합니다. 공유 사서함에 대해 보관을 사용하도록 설정하려면 Exchange Online 계획 2 라이선스 또는 Exchange Online 라이선스가 있는 Exchange Online Archiving 계획 1 라이선스가 필요합니다.

## <a name="how-auto-expanding-archiving-works"></a>자동 확장 보관의 작동 방식

앞서 설명한 것 처럼 사용자의 보관 사서함을 사용하도록 설정하면 추가 사서함 저장소 공간이 만들어집니다. 자동 확장 보관을 사용하도록 설정하면 Microsoft 365 사서함의 크기를 정기적으로 확인합니다. 보관 사서함이 저장소 제한에 가까워지면 보관 Microsoft 365 추가 저장소 공간을 자동으로 만듭니다. 사용자가 이러한 추가 저장소 공간을 사용할 수 Microsoft 365 저장소 공간을 더 추가할 수 있습니다. 이 프로세스는 자동으로 수행됩니다. 즉, 관리자가 추가 보관 저장소를 요청하거나 자동 확장 보관을 관리할 필요가 없습니다.

다음은 프로세스에 대한 간략한 개요입니다.

![자동 확장 보관 프로세스 개요](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 사용자 사서함 또는 공유 사서함에 대해 보관을 사용하도록 설정합니다. 저장소 공간이 100GB인 보관 사서함이 만들어지며 보관 사서함에 대한 경고 할당량은 90GB로 설정됩니다.

2. 관리자는 사서함에 대해 자동 확장 보관을 사용할 수 있습니다. 보관 사서함(복구 가능한 항목 폴더 포함)이 90GB에 도달하면 자동 확장 보관함으로 변환되고 Microsoft 365 추가됩니다. 추가 저장소 공간을 프로비전하는 데 최대 30일이 걸릴 수 있습니다.

   > [!NOTE]
   > 사서함이 보류 중이거나 보존 정책에 할당된 경우 자동 확장 보관을 사용하도록 설정하면 보관 사서함의 저장소 할당량은 110GB로 증가합니다. 마찬가지로 보관 경고 할당량은 100GB로 증가합니다.

3. Microsoft 365 경우 저장소 공간이 자동으로 추가됩니다.

> [!IMPORTANT]
> 자동 확장 보관은 하루 1GB를 초과하지 않는 증가 속도의 개별 사용자(또는 공유 사서함)에 사용되는 사서함에만 지원됩니다. 사용자의 보관 사서함은 해당 사용자만을 위한 것입니다. 저널링, 전송 규칙 또는 자동 전달 규칙을 사용하여 메시지를 보관 사서함에 복사할 수 없습니다. Microsoft는 사용자의 보관 사서함이 다른 사용자의 보관 데이터를 저장하는 데 사용되는 경우 또는 부적절한 사용의 다른 경우에 무제한 보관을 거부할 수 있는 권리가 있습니다.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>추가 보관 저장소 공간으로 이동하는 이유는 무엇입니까?

자동 확장 보관 저장소를 효율적으로 사용하기 위해 폴더가 이동될 수 있습니다. Microsoft 365 저장소가 추가될 때 이동되는 폴더를 확인합니다. 폴더를 이동할 때 하나 이상의 하위 폴더가 자동으로 만들어지며 원본 폴더의 항목이 이러한 폴더에 배포되어 이동 프로세스를 용이하게 하는 경우도 있습니다. 폴더 목록의 보관 부분을 볼 Outlook 이러한 하위 폴더는 원래 폴더 아래에 표시됩니다.  이러한 하위 Microsoft 365 이름을 지정하는 데 사용하는 명명 규칙은 **\<folder name\> _yyyy(mmm dd, yyyy h_mm)입니다.** 여기서

- **yyyy는** 폴더의 메시지를 받은 연도입니다.

- **mmm dd, yyyyy** h_m 는 Office 365 UTC 형식의 하위폴더를 만든 날짜와 시간으로, Outlook.

다음 스크린샷은 메시지가 자동 확장 보관함으로 이동되기 전과 후에 폴더 목록을 보여 주며,

 **추가 저장소가 추가되기 전에**

![자동 확장 보관이 프로비전되기 전 보관 사서함의 폴더 목록입니다.](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **추가 저장소 추가 후**

![자동 확장 보관이 프로비전된 후 보관 사서함의 폴더 목록입니다.](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 앞서 Microsoft 365 항목을 하위폴더로 이동하고 위에 설명된 명명 규칙을 사용하여 이름을 변경하여 보조 보관함으로 콘텐츠를 배포할 수 있습니다. 그러나 항목을 하위폴더로 이동하는 경우도 있을 수 있습니다. 경우에 따라 전체 폴더가 보조 보관함으로 이동될 수 있습니다. 이 경우 폴더는 원래 이름을 그대로 하게 됩니다.  폴더가 보조 보관함으로 Outlook 폴더 목록에는 분명하지 않습니다.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook 확장된 보관함의 항목에 액세스하기 위한 요구 사항

자동 확장 보관 파일에 저장된 메시지에 액세스하기 위해 사용자는 다음 클라이언트 중 하나를 Outlook 합니다.

- Outlook 2016 Outlook 또는 Windows

- 웹용 Outlook

- Outlook 2016 또는 Outlook 2019 for Mac

자동 확장 보관 파일에 저장된 메시지에 액세스하기 위해 Outlook 웹용 Outlook 고려할 몇 가지는 다음과 같습니다.

- 자동 확장 저장소 영역으로 이동된 폴더를 포함하여 보관 사서함의 모든 폴더에 액세스할 수 있습니다.

- 보관 사서함에 자동 확장된 저장소 영역이 하나 이상 있는 경우 보관 사서함 또는 보조 보관함에서 폴더를 삭제할 수 없습니다. 즉, 자동 확장 저장소 영역이 프로비전된 후 보관함의 폴더를 삭제할 수 없습니다.

- 자동 확장 저장소 영역의 항목을 삭제할 수 있습니다. 그러나 자동 확장 저장소 영역의 삭제된 항목을 복구하는 데는 지우기 항목 복구 기능을 사용할 수 없습니다.

- 자동 확장 보관 검색은 OWA(웹용 Outlook 검색)에서 사용할 수 있습니다. 온라인 보관과 마찬가지로 추가 저장소 영역으로 이동된 항목을 검색할 수 있습니다. OWA에서 보관함이 검색 범위로 선택되어 있는 경우 모든 보관함(자동 확장된 보관함 포함)과 해당 하위폴더가 검색됩니다.

- 자동 확장 보관 검색은 현재 채널의 Outlook 데스크톱(미리 보기)에서 사용할 수 있습니다. 이 미리 보기 내에서 현재 사서함 범위를 사용할 수 있어 자동 확장된 보관 파일을 검색할 수 있습니다. 이 기능 및 기타 Microsoft Search 지원 기능에 대한 자세한 내용은 에 연결된 Outlook Windows 기능의 Exchange Online 를 [Microsoft Search.](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045) 

- 자동 확장된 Outlook 및 읽기/Outlook 읽지 않은 웹용 Outlook 수가 정확하지 않을 수 있습니다.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>자동 확장 보관 및 기타 규정 준수 기능

이 섹션에서는 자동 확장 보관과 기타 규정 준수 및 데이터 거버넌스 기능 간의 기능에 대해 설명합니다.

- **eDiscovery:** 콘텐츠 검색 또는 eDiscovery와 같은 eDiscovery 도구를 In-Place 자동 확장 보관함의 추가 저장소 영역도 검색됩니다.

- **보존:** 보안 및 규정 준수 센터의 Exchange Online 또는 eDiscovery 사례 보류 및 보존 정책과 같은 도구를 사용하여 사서함을 보류하면 자동 확장된 보관함에 있는 콘텐츠도 보류됩니다.

- **MRM(메시징 레코드 관리):** 사서함에서 MRM 삭제 정책을 Exchange Online 만료된 사서함 항목을 영구적으로 삭제하면 자동 확장 보관함에 있는 만료된 항목도 삭제됩니다.

- **서비스 가져오기:** 가져오기 Office 365 사용하여 PST 파일을 사용자의 자동 확장 보관함으로 가져올 수 있습니다. PST 파일에서 사용자의 보관 사서함으로 최대 100GB의 데이터를 가져올 수 있습니다.

## <a name="more-information"></a>추가 정보

자동 확장 보관에 대한 자세한 기술 정보는 Microsoft 365: 자동 확장 [보관함 FAQ를 참조합니다.](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)
