---
title: DLP 정책에서 민감도 레이블을 조건으로 사용
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: DLP 정책에서 민감도 레이블을 조건으로 사용할 수 있는 서비스 및 항목 형식에 대해 배워봅니다.
ms.openlocfilehash: b74911765d9249834553c09bbd4efdd02e5f97ce
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163399"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>DLP 정책에서 민감도 레이블을 조건으로 사용

[민감도 레이블](sensitivity-labels.md)을 이들 위치에서 DLP 정책의 조건으로 사용할 수 있습니다.

- Exchange Online 전자 메일 메시지
- SharePoint Online
- 비즈니스용 OneDrive 사이트
- Windows 10 장치

민감도 레이블은 **콘텐츠가 포함하는** 목록에 옵션으로 표시됩니다.

> [!div class="mx-imgBorder"]
> ![조건으로서의 민감도 레이블.](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> DLP 정책을 적용할 위치로 **Teams 대화 및 채널 메시지** 를 선택한 경우 조건별 **민감도 레이블** 을 사용할 수 없습니다.


## <a name="supported-items-scenarios-and-policy-tips"></a>지원되는 항목, 시나리오 및 정책 팁

이러한 항목 및 이러한 시나리오에 대해 민감도 레이블을 조건으로 사용할 수 있습니다.

### <a name="supported-items"></a>지원되는 항목

|서비스  |항목 종류  |사용 가능한 정책 팁  |적용 가능  |
|---------|---------|---------|---------|
|Exchange    |전자 메일 메시지         |예         |예         |
|Exchange    |전자 메일 첨부 파일         |아니요         |예*         |
|SharePoint Online     |SharePoint Online의 항목         |예         |예         |
|비즈니스용 OneDrive     |항목         |예         |예         |
|Teams     |Teams 채팅 및 채널 메시지         |해당 없음         |해당 없음         |
|Teams     |첨부 파일         |예 **         |예 **         |
|Windows 10 장치     |항목         |예         |예         |
|MCAS (미리 보기) |항목         |예         |예         |

민감도 레이블이 부착된 전자 메일 첨부 파일의 \* DLP 감지는 Office 파일 형식에만 지원됩니다.

\** 1:1 채팅 혹은 채널을 통해 Teams 로 보낸 첨부 파일은 비즈니스용 One drive 및 SharePoint에 자동으로 업로드 됩니다. 따라서 SharePoint Online 또는 비즈니스용 One Drive가 DLP 정책에서 위치로 포함되는 경우, Teams에서 보낸 레이블이 지정된 첨부 파일은 이 조건의 범위에 자동으로 포함됩니다. DLP 정책에서 Teams를 위치로 선택할 필요가 없습니다.

> [!NOTE]
> SharePoint 및 비즈니스용 OneDrive에서 민감도 레이블을 검색하는 DLP의 기능은 제한적입니다. 자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md#limitations)을 참조하세요.

### <a name="supported-scenarios"></a>지원되는 시나리오

- DLP 관리자는 하나 이상의 민감도 레이블을 조건으로 포함하도록 선택할 때 테넌트의 모든 민감도 레이블 목록을 볼 수 있습니다.

- 위의 지원 매트릭스에 표시된 대로 민감도 레이블을 조건으로 사용하는 것은 모든 워크로드에서 지원됩니다.

- DLP 정책 팁은 민감도 레이블을 조건으로 포함하는 DLP 정책에 대해 작업 전반에 결쳐 계속해서 표시됩니다(Outlook Win32 제외)

- 민감도 레이블이 조건과 일치하는 DLP 정책에서 일치하는 경우 민감도 레이블도 인시던트 보고서 전자 메일의 일부로서 표시됩니다.

- 민감도 레이블 세부 정보는 또한 민감도 레이블이 조건으로 포함된 DLP 정책 일치에 대한 DLP 규칙 일치 감사 로그에도 표시됩니다.


### <a name="support-policy-tips"></a>지원 정책 팁


|워크로드  |지원되는/지원되지 않는 정책 팁  |
|---------|---------|
|OWA |    지원     |
|Outlook Win 32    |  지원되지 않음       |
|SharePoint   |   지원      |
|비즈니스용 OneDrive    |    지원     |
|끝점 장치   |  지원되지 않음       |
