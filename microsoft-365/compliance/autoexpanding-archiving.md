---
title: 자동 확장 보관 개요
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Exchange Online 사서함에 대한 추가 보관 저장소를 제공하는 자동 확장 보관에 대해 알아보세요.
ms.openlocfilehash: d1833416ad4ff1d2dbb3241fde466e31bb6d8a74
ms.sourcegitcommit: 53a4ee148348010444f7deb0590d34e6a298adb8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2021
ms.locfileid: "60400050"
---
# <a name="overview-of-auto-expanding-archiving"></a>자동 확장 보관 개요

Office 365에서 보관 사서함은 사용자에게 추가 사서함 저장 공간을 제공합니다. 사용자의 보관 사서함이 활성화되면 최대 100GB의 추가 저장소를 사용할 수 있습니다. 과거에는 100GB 저장소 할당량에 도달하면 조직에서 Microsoft에 연락하여 보관 사서함을 위한 추가 저장 공간을 요청해야 했습니다. 이제는 더 이상 그렇지 않습니다.

Microsoft 365의 보관 기능(*자동 확장 보관*)은 보관 사서함에 최대 1.5TB의 추가 저장소를 제공합니다. 보관 사서함의 저장소 할당량에 도달하면 Microsoft 365는 보관 사서함이 1.5TB에 도달할 때까지 보관 크기를 자동으로 (그리고 증분적으로) 늘립니다.

자동 확장 보관 설정에 대한 단계별 지침은 [자동 확장 보관 사용](enable-autoexpanding-archiving.md)을 참조하세요.

> [!NOTE]
> 자동 확장 보관 기능은 공유 사서함도 지원합니다. 공유 사서함에 보관 기능을 사용하도록 설정하려면, Exchange Online 보관 라이선스가 있는 Exchange Online 계획 1 라이선스 또는 Exchange Online 계획 2 라이선스가 있어야 합니다.

## <a name="how-auto-expanding-archiving-works"></a>자동 확장 보관의 작동 방식

앞에서 설명한 것처럼 사용자의 보관 사서함이 사용되면 추가 사서함 저장 공간이 생성됩니다. 자동 확장 보관을 사용하도록 설정하면 Microsoft 365에서 보관 사서함의 크기를 주기적으로 확인합니다. 보관 사서함이 저장소 제한에 가까워지면 Microsoft 365는 자동으로 보관을 위한 추가 저장 공간을 만듭니다. 사용자에게 이 추가 저장 공간이 부족하면 Microsoft 365는 사용자 보관함에 더 많은 저장 공간을 추가합니다. 이 프로세스는 사용자의 보관함 크기가 1.5TB에 도달할 때까지 계속됩니다. 이 프로세스는 자동으로 이루어지므로 관리자가 추가 보관함 저장소를 요청하거나 자동 확장 보관 기능을 관리할 필요가 없습니다.

다음은 프로세스에 대한 간략한 개요입니다.

![자동 확장 보관 프로세스의 개요입니다.](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 사용자 사서함 또는 공유 사서함에 대해 보관 기능을 사용하도록 설정됩니다. 100GB의 저장 공간이 있는 보관 사서함이 생성되고 보관 사서함에 대한 경고 할당량이 90GB로 설정됩니다.

2. 관리자는 사서함에 대해 자동 확장 보관을 사용합니다. 보관 사서함(복구 가능한 항목 폴더 포함)이 90GB에 도달하면 자동 확장 보관으로 변환되고 Microsoft 365는 보관 공간이 최대 1.5TB에 도달할 때까지 저장 공간을 추가합니다. 추가 저장 공간을 프로비전하는 데 최대 30일이 소요될 수 있습니다.

   > [!NOTE]
   > 사서함이 보류 중이거나 보존 정책에 할당된 경우 자동 확장 보관을 사용하도록 설정하면 보관 사서함의 저장소 할당량이 110GB로 증가합니다. 마찬가지로 보관함 경고 할당량이 100GB로 증가합니다.

3. Microsoft 365는 필요에 따라 자동으로 더 많은 저장 공간을 추가합니다.

> [!IMPORTANT]
> 자동 확장 보관은 일일 1GB를 초과하지 않는 증가율로 개별 사용자(또는 공유 사서함)에 사용되는 사서함에 대해서만 지원됩니다. 사용자의 보관 사서함은 해당 사용자만을 위한 것입니다. 저널링, 전송 규칙 또는 자동 전달 규칙을 사용하여 메시지를 보관 사서함에 복사하는 것은 허용되지 않습니다. Microsoft는 사용자의 보관 사서함이 다른 사용자를 위한 보관 데이터를 저장하는 데 사용되는 경우 또는 기타 부적절한 사용의 경우에 추가 보관을 거부할 권리가 있습니다.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>추가 보관함 저장 공간으로 이동되는 것은 항목은 무엇인가요?

자동 확장 보관함 저장소를 효율적으로 사용하기 위해 폴더가 이동할 수 있습니다. Microsoft 365는 보관함에 추가 저장소가 추가될 때 이동할 폴더를 결정합니다. 경우에 따라 폴더가 이동될 때 하나 이상의 하위 폴더가 자동으로 생성되고 원래 폴더의 항목이 이동 프로세스를 용이하게 하기 위해 이러한 폴더에 배포됩니다. Outlook에서 폴더 목록의 보관함 부분을 볼 때 이러한 하위 폴더는 원래 폴더 아래에 표시됩니다. Microsoft 365에서 이러한 하위 폴더의 이름을 지정하는 데 사용하는 명명 규칙은 **\<folder name\>_yyyy(Created on mmm dd, yyyy h_mm)** 입니다. 여기서:

- **yyyy** 는 폴더의 메시지가 수신된 연도입니다.

- **mmm dd, yyyy h_m** 은 Outlook의 사용자 시간대 및 지역 설정을 기반으로 Office 365에서 UTC 형식으로 하위 폴더를 만든 날짜 및 시간입니다.

다음 스크린샷은 메시지가 자동 확장 보관함으로 이동되기 전과 후의 폴더 목록을 보여줍니다.

 **추가 저장소가 추가되기 전**

![자동 확장 보관이 프로비전되기 전 보관 사서함의 폴더 목록입니다.](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **추가 저장소가 추가된 후**

![자동 확장 보관이 프로비전된 후 보관 사서함의 폴더 목록입니다.](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 앞에서 설명한 대로 Microsoft 365는 항목을 하위 폴더로 이동하고 위에서 설명한 명명 규칙을 사용하여 항목의 이름을 지정하여 콘텐츠를 보조 보관함에 배포하는 데 도움이 됩니다. 그러나 항목이 항상 하위 폴더로 이동하는 것은 아닙니다. 경우에 따라 전체 폴더가 보조 보관함으로 이동할 수 있습니다. 이 경우 폴더는 원래 이름을 유지합니다.  Outlook의 폴더 목록에서 폴더가 보조 보관함으로 이동되었는지는 분명하지 않습니다.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>자동 확장 보관함의 항목에 액세스하기 위한 Outlook 요구 사항

자동 확장 보관함에 저장된 메시지에 액세스하려면 사용자는 다음 Outlook 클라이언트 중 하나를 사용해야 합니다.

- Windows용 Outlook 2016 또는 Outlook 2019

- 웹용 Outlook

- Mac용 Outlook 2016 또는 Outlook 2019

다음은 Outlook 또는 웹용 Outlook을 사용하여 자동 확장 보관함에 저장된 메시지에 액세스할 때 고려해야 할 몇 가지 사항입니다.

- 자동 확장된 저장 영역으로 이동된 폴더를 포함하여 보관 사서함의 모든 폴더에 액세스할 수 있습니다.

- 보관 사서함에 자동 확장된 저장 영역이 하나 이상 있는 경우 보관 사서함이나 보조 보관함에서 폴더를 삭제할 수 없습니다. 즉, 자동 확장된 저장 영역이 프로비저전 후에는 보관함에서 폴더를 삭제할 수 없습니다.

- 자동 확장된 저장 영역에서 항목을 삭제할 수 있습니다. 그러나 사서함에 대해 자동 확장 보관 기능이 사용된 후에는 지운 항목 복구 기능을 사용하여 항목을 복구할 수 없습니다.

- 자동 확장 보관 검색은 웹용 Outlook(OWA)에서 사용할 수 있습니다. 온라인 보관함과 유사하게 추가 저장 영역으로 이동된 항목을 검색할 수 있습니다. OWA에서 보관함이 검색 범위로 선택되면 모든 보관함(자동 확장 보관함 포함) 및 해당 하위 폴더가 검색됩니다.

- 자동 확장 보관함 검색은 Outlook 데스크톱의 현재 채널(미리 보기)에서 사용할 수 있습니다. 이 미리 보기 내에서 현재 사서함 범위를 사용할 수 있으므로 자동 확장 보관함을 검색할 수 있습니다. 이 기능 및 기타 Microsoft Search 지원 기능에 대한 자세한 내용은 [Exchange Online에 연결된 Windows용 Outlook이 Microsoft Search를 활용하는 방법](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)을 참조하세요. 

- Outlook의 항목 수 및 자동 확장 보관함의 읽음/읽지 않음 수(Outlook 및 웹용 Outlook)는 정확하지 않을 수 있습니다.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>자동 확장 보관 및 기타 규정 준수 기능

이 섹션에서는 자동 확장 확장과 기타 규정 준수 및 데이터 거버넌스 기능 사이의 기능성에 대해 설명합니다.

- **eDiscovery:** Content Search 또는 In-Place eDiscovery와 같은 eDiscovery 도구를 사용하는 경우 자동 확장 보관함의 추가 저장 영역도 검색됩니다.

- **보존:** Exchange Online의 소송 보존 또는 보안 및 규정 준수 센터의 eDiscovery 케이스 보존 및 보존 정책과 같은 도구를 사용하여 사서함을 보류하면 자동 확장 보관함에 있는 콘텐츠도 보존으로 배치됩니다.

- **MRM(메시징 레코드 관리):** Exchange Online에서 MRM 삭제 정책을 사용하여 만료된 사서함 항목을 영구적으로 삭제하면 자동 확장 보관함에 있는 만료된 항목도 삭제됩니다.

- **가져오기 서비스:** Office 365 가져오기 서비스를 사용하여 PST 파일을 사용자의 자동 확장 보관함으로 가져올 수 있습니다. PST 파일에서 사용자의 보관 사서함으로 최대 100GB의 데이터를 가져올 수 있습니다.

## <a name="more-information"></a>자세한 정보

자동 확장 보관에 대한 자세한 기술 정보는 [Microsoft 365: 자동 확장 보관함 FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)를 참조하세요.
