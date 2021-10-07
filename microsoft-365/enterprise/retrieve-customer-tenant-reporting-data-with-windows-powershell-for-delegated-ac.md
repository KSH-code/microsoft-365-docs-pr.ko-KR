---
title: DAP 파트너에 대한 사용자 지정을 사용하여 Windows PowerShell 보고 데이터 검색
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: '요약: Microsoft Exchange Online용 원격Windows PowerShell을 사용하여 개별 고객 테넌트에서 보고서를 검색합니다.'
ms.openlocfilehash: cc9046ab5c90dcb40cbf012772fd80b56f71ec79
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163255"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>DAP(위임된 액세스 권한) 파트너용 Windows PowerShell을 사용하여 고객 테넌트 보고 데이터 검색

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

원격 Windows PowerShell 사용하여 Microsoft Exchange Online 테넌트에서 보고서를 검색할 수 있습니다.

Syndication 및 클라우드 솔루션 공급자(CSP) 파트너는 PowerShell용 원격 서비스를 통해 직접 고객 테넌트 보고서를 Windows PowerShell 데이터에 액세스할 Exchange Online 있습니다. 이를 통해 파트너는 보고 데이터를 수집하고 저장한 후 여기에서 다른 작업을 수행할 수 있습니다. 원격 연결을 연 후 고객 테넌트에 대한 보고 데이터 검색은 고객 테넌트에 대해 cmdlet을 실행하는 것과 동일합니다.

이 문서에서는 원격 Windows PowerShell 사용하여 Exchange Online 테넌트에 연결하고 보고서를 검색합니다. 기본적으로 Windows PowerShell 테넌트의 보고 데이터 집계를 지원하지 않습니다. 이 절차를 사용하여 검색하는 보고서는 연결하는  _DelegatedOrg에만_ 해당합니다.

## <a name="before-you-begin"></a>시작하기 전에

- 원격 Windows PowerShell을 사용하여 Exchange Online 테넌트에 연결해야 합니다. 자세한 내용은 [DAP(위임된 액세스 권한) 파트너용 원격 Windows PowerShell을 사용하여 Exchange Online 테넌트에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

## <a name="run-the-get-stalemailboxreport-sample"></a>Get-StaleMailboxReport 샘플 실행

원격 세션을 Exchange Online으로 연 후 이 명령을 실행하여 날짜 범위 2015/03/25에서 2015/03/31까지에 대해 **Get-StaleMailboxReport** 를 검색합니다.

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

사용할 수 있는 메시지 추적에 대해 Exchange Online, Lync Online, SharePoint Online 등에 다양한 보고 cmdlet을 사용할 수 있습니다. 사용 가능한 보고 cmdlet 및 Office 365 보고 웹 서비스에 대한 자세한 내용은 다음 섹션의 항목을 참조하세요.

## <a name="see-also"></a>참고 항목

[Office 365 보고 웹 서비스](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Exchange Online의 보고 cmdlet](/powershell/module/exchange/get-csclientdevicedetailreport)

[파트너를 위한 도움말](https://go.microsoft.com/fwlink/p/?LinkID=533477)
