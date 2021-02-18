---
title: 보고서 대시보드에서 Office 365용 Defender 보고서 보기
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 보안 및 준수 센터에서 Microsoft Defender for Office 365에 대한 보고서를 & 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e5d48f6ac8f6246b65761f5728405c37333d71
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286600"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>보안 및 준수 센터의 보고서 대시보드에서 Office 365용 & 보기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Office 365 조직용 Microsoft Defender(예: Microsoft 365 E5 구독 또는 Office 365 계획 1용 Microsoft Defender 또는 Office 365 계획 2 추가 기능용 Microsoft Defender)에는 다양한 보안 관련 보고서가 포함되어 있습니다. 필요한 사용 [](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)권한이 있는 경우 보고서 대시보드로 & 보안 및 준수 센터에서 이러한 보고서를 볼 **수** \> **있습니다.** 보고서 대시보드로 직접 이동하기 위해 를 <https://protection.office.com/insightdashboard> 열습니다.

![보안 및 준수 센터의 & 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Office 365용 Defender 파일 형식 보고서

**Office 365용 Defender** 파일 형식 보고서에는 안전한 첨부 파일에서 악성으로 감지된 파일 [형식이 표시됩니다.](atp-safe-attachments.md)

 보고서의 집계 보기는 90일 동안 필터링할 수 있는 반면 세부 정보 보기는 10일 동안의 필터링만 허용합니다.

보고서를 보고 보안 및 준수 [센터를 &](https://protection.office.com)보고서  대시보드로 이동하여 Office 365 파일 형식에 대한 \>  **Defender를 선택합니다.** 보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=ATPFileReport> 있습니다.

![보고서 대시보드에서 Office 365 파일 형식의 Defender 위젯](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> 이 보고서의 정보는 [Office 365용 Defender](#defender-for-office-365-message-disposition-report)메시지 처리 보고서에서도 사용할 수 있습니다.

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Office 365용 Defender 파일 형식 보고서에 대한 보고서 보기

다음 보기를 사용할 수 있습니다.

- **데이터 보기: 파일:** 차트에 다음 정보가 포함되어 있습니다.

  - **악의적인 Excel 첨부 파일**
  - **악성 플래시 첨부 파일**
  - **악성 PDF 첨부 파일**
  - **악성 PowerPoint 첨부 파일**
  - **악의적인 URL**
  - **악성 Word 첨부 파일**
  - **악성 실행 파일 첨부 파일**
  - **기타**

  특정 일(데이터 포인트)에 마우스를 대면 [EOP의](anti-malware-protection.md)안전 첨부 파일 및 [](atp-safe-attachments.md) 맬웨어 방지 보호 기능에서 검색된 악성 파일 유형의 분석 정보를 볼 수 있습니다.

  ![Office 365용 Defender 파일 형식 보고서의 파일 보기](../../media/atp-file-types-report-file-view.png)

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에 표시되는 동일한 파일 형식 값입니다.

- **데이터 보기: 메시지:** 차트에 다음 정보가 포함되어 있습니다.

  - **액세스 차단**
  - **대체된 메시지**
  - **모니터링된 메시지**
  - **동적 전자 메일 배달로** 대체: 자세한 내용은 안전 첨부 파일 정책에서 동적 [배달을 참조하세요.](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Office 365용 Defender 파일 형식 보고서의 메시지 보기](../../media/atp-file-types-report-message-view.png)

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에서 사용할 수 있는 동일한 메시지 처리 값과 추가 메시지 값이 **전달됩니다.**

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Office 365용 Defender 파일 형식 보고서에 대한 세부 정보 테이블 보기

세부 정보 표 보기를 클릭하면 보고서에서 지난 10일 동안 조직 내에서 발생된 모든 클릭 수를 거의 실시간으로 볼 수 있습니다. 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.

- **데이터 보기: 파일:**

  - **날짜**
  - **받는 사람 주소**
  - **보낸 사람 주소**
  - **메시지 ID:** 메시지 헤더의 **Message-ID** 헤더 필드에서 사용할 수 있으며 고유해야 합니다. 값의 예로는 괄호를 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 들 수 있습니다.
  - **파일**

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에 표시되는 동일한 파일 형식 값입니다.

- **데이터 보기: 메시지:**

  - **날짜**
  - **받는 사람 주소**
  - **보낸 사람 주소**
  - **메시지 ID**
  - **파일**
  - **제목**

  필터를 **클릭하면** 다음 필터를 사용하여 결과를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에서 사용할 수 있는 동일한 메시지 처리 값과 추가 메시지 값이 **전달됩니다.**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="defender-for-office-365-message-disposition-report"></a>Office 365용 Defender 메시지 처리 보고서

**ATP 메시지 처리 보고서에는** 악성 콘텐츠가 있는 것으로 감지된 전자 메일 메시지에 대해 수행된 작업이 표시됩니다.

보고서를 확인하려면 보안 및 준수 [센터를 &](https://protection.office.com)보고서  대시보드로 이동하여 Office 365 메시지 처리를 위한 \>  **Defender를 선택합니다.** 보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=ATPMessageReport> 있습니다.

![보고서 대시보드의 Office 365 메시지 처리 위젯에 대한 Defender](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> 이 보고서의 정보는 [Office 365용 Defender](#defender-for-office-365-file-types-report)파일 형식 보고서에서도 사용할 수 있습니다.

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Office 365용 Defender 메시지 처리 보고서에 대한 보고서 보기

다음 보기를 사용할 수 있습니다.

- **데이터 보기: 메시지:** 차트에 다음 정보가 포함되어 있습니다.

  - **액세스 차단**
  - **대체된 메시지**
  - **모니터링된 메시지**
  - **동적 전자 메일 배달로** 대체: 자세한 내용은 안전 첨부 파일 정책에서 동적 [배달을 참조하세요.](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Office 365용 Defender 파일 형식 보고서의 메시지 보기](../../media/atp-file-types-report-message-view.png)

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에서 사용할 수 있는 동일한 메시지 처리 값과 추가 메시지 값이 **전달됩니다.**

- **데이터 보기: 파일:** 차트에 다음 정보가 포함되어 있습니다.

  - **악의적인 Excel 첨부 파일**
  - **악성 플래시 첨부 파일**
  - **악성 PDF 첨부 파일**
  - **악성 PowerPoint 첨부 파일**
  - **악의적인 URL**
  - **악성 Word 첨부 파일**
  - **악성 실행 파일 첨부 파일**
  - **기타**

  특정 일(데이터 포인트)에 마우스를 대면 [EOP의](anti-malware-protection.md)안전 첨부 파일 및 [](atp-safe-attachments.md) 맬웨어 방지 보호 기능에서 검색된 악성 파일 유형의 분석 정보를 볼 수 있습니다.

  ![Office 365용 Defender 파일 형식 보고서의 파일 보기](../../media/atp-file-types-report-file-view.png)

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에 표시되는 동일한 파일 형식 값입니다.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Office 365용 Defender 메시지 처리 보고서에 대한 세부 정보 테이블 보기

세부 정보 표 보기를 클릭하면 보고서에서 지난 10일 동안 조직 내에서 발생된 모든 클릭 수를 거의 실시간으로 볼 수 있습니다. 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.

- **데이터 보기: 메시지:**

  - **날짜**
  - **받는 사람 주소**
  - **보낸 사람 주소**
  - **메시지 ID**
  - **파일**
  - **제목**

  필터를 **클릭하면** 다음 필터를 사용하여 결과를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에서 사용할 수 있는 동일한 메시지 처리 값과 추가 메시지 값이 **전달됩니다.**

- **데이터 보기: 파일:**

  - **날짜**
  - **받는 사람 주소**
  - **보낸 사람 주소**
  - **메시지 ID**
  - **파일**

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 차트에 표시되는 동일한 파일 형식 값입니다.

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="mail-latency-report"></a>메일 대기 시간 보고서

메일 **대기 시간 보고서에는** 조직 내에서 발생된 메일 배달 및 확인 대기 시간에 대한 집계 보기가 표시됩니다. 서비스의 메일 배달 시간은 다양한 요인의 영향을 받지만 절대 배달 시간(초)은 성공 또는 문제를 나타내는 좋은 지표가 아닙니다. 하루의 배달 시간이 느리면 다른 날의 평균 배달 시간으로 간주되거나 그 반대의 경우도 마찬가지입니다. 메일 **대기 시간 보고서는** 다른 메시지의 관찰된 배달 시간에 대한 통계 데이터를 기반으로 메시지 배달을 한정합니다.

- **50번째 백분위수:** 메시지 배달 시간의 중간입니다. 이 값은 평균 배달 시간으로 고려할 수 있습니다.
- **90번째 백분위수:** 메시지 배달 대기 시간이 길어질 수 있습니다. 메시지의 10%만 배달하는 데 이 값보다 오래 걸렸다.
- **99번째 백분위수:** 메시지 배달의 가장 높은 대기 시간을 나타냅니다.

클라이언트 쪽 및 네트워크 대기 시간은 포함되지 않습니다.

보고서를 확인하려면 Security & 준수 센터를 열고  보고서 [대시보드로](https://protection.office.com)이동하여 메일 대기 시간 보고서를 \>  **선택합니다.** 보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/mailLatencyReport?viewid=P50> 있습니다.

![보고서 대시보드의 메일 대기 시간 보고서 위젯](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>메일 대기 시간 보고서에 대한 보고서 보기

보고서를 열면 기본적으로 **50번째** 백분위수 탭이 선택됩니다.

기본적으로 이 보기에는 다음 필터로 구성된 차트가 포함되어 있습니다.

- **날짜:** 지난 7일
- **메시지 보기:**
  - 확인된 메시지

이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.

- **메일 배달 대기 시간**
- **데스토인 대기 시간**

차트에서 범주 위에 마우스를 대면 각 범주의 대기 시간 분석이 표시됩니다.

![메일 대기 시간 보고서](../../media/mail-latency-report.png)

보고서 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- 모든 메시지
- 첨부 파일 또는 URL이 포함된 메시지

**90번째** 백분위수 탭 또는 **99번째** 백분위수 탭을 클릭하면 **50번째** 백분위수 보기의 동일한 기본 필터가 사용됩니다.

### <a name="details-table-view-for-the-mail-latency-report"></a>메일 대기 시간 보고서에 대한 세부 정보 테이블 보기

세부 정보 표 보기에는 다음 정보가 표시됩니다.

- **날짜**
- **백분위수**
- **메시지 수**
- **전체 대기 시간**

![메일 대기 시간 보고서 세부 정보](../../media/mail-latency-report-details.png)

위의 예는 11월 14일 배달 및 확인된 모든 메시지의 평균 대기 시간이 **108.033초인 것으로 나타났습니다.**

세부 정보 테이블에는 각 탭에서 동일한 정보가 포함되어 있습니다.

## <a name="threat-protection-status-report"></a>위협 방지 상태 보고서

**위협 방지** 상태 보고서는 EOP(Exchange [Online Protection)](exchange-online-protection-overview.md) 및 Office 365용 Microsoft Defender에서 검색 및 차단되는 악의적인 콘텐츠 및 악의적인 전자 메일에 대한 정보를 수집하는 단일 보기입니다. 자세한 내용은 위협 방지 상태 [보고서를 참조하세요.](view-email-security-reports.md#threat-protection-status-report)

## <a name="url-threat-protection-report"></a>URL 위협 방지 보고서

**URL 위협 방지 보고서는** 검색된 위협에 대한 요약 및 추세 보기와 안전한 링크의 일부로 URL 클릭 시 [수행되는 작업을 제공합니다.](atp-safe-links.md) 이 보고서에는 적용된 안전 링크 정책에 사용자 클릭 추적 금지 옵션이 선택된 사용자의 클릭 데이터가 **없습니다.**

보고서를 확인하려면 Security & 준수 센터를 열고  보고서 [대시보드로](https://protection.office.com)이동한 다음 URL 보호 보고서를 \>  **선택합니다.** 보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 있습니다.

![보고서 대시보드의 URL 보호 보고서 위젯](../../media/url-protection-report-widget.png)

> [!NOTE]
> 이는 데이터가 *더* 큰 데이터 집합의 추세를 나타내는 보호 추세 보고서입니다. 따라서 여기에서 집계 보기의 데이터를 실시간으로 사용할 수 없지만 세부 정보 테이블 보기의 데이터는 있으므로 두 보기 간에 약간의 불일치가 표시될 수 있습니다.

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 위협 방지 보고서에 대한 보고서 보기

**URL 위협 방지 보고서에는** 지난 90일 동안의 데이터를 표시하는 4시간마다 새로 고쳐진 두 개의 집계 보기가 있습니다.

- **URL 클릭 보호 작업:** 조직의 사용자가 클릭한 URL 클릭 수와 클릭 결과를 보여줍니다.

  - **차단(사용자가** URL로 이동하지 차단)
  - **차단 및 클릭**
  - **검사 중 클릭**

  클릭은 사용자가 차단 페이지를 통해 악성 웹 사이트로 이동했다는 것을 나타냅니다(관리자는 안전한 링크 정책에서 클릭을 사용하지 않도록 설정할 수 있습니다).

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 사용 가능한 클릭 보호 작업과 허용되는 값(사용자가 URL로 이동하도록 허용)을 더한 값입니다. 

  ![URL 위협 방지 보고서의 URL 클릭 보호 작업 보기](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **응용 프로그램당 URL 클릭:** 안전한 링크를 지원하는 응용 프로그램의 URL 클릭 수를 보여 주며,

  - **전자 메일 클라이언트**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **기타**

  필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.

  - **시작 날짜** 및 **종료 날짜**
  - 사용 가능한 응용 프로그램

### <a name="details-table-view-for-the-url-threat-protection-report"></a>URL 위협 방지 보고서에 대한 세부 정보 테이블 보기

세부 정보 보기 테이블을 클릭하면 보고서에서 다음 세부 정보를 통해 지난 7일 동안 조직 내에서 발생된 모든 클릭을 거의 실시간으로 볼 수 있습니다.

- **클릭 시간**
- **사용자**
- **URL**
- **작업**
- **앱**

세부 정보 테이블 보기에서 **필터를** 클릭하면 보고서 보기와 동일한 조건에 따라 필터링할 수  있으며 도메인 또는 받는 사람도 콤보로 구분하여 필터링할 수 있습니다. 

> [!NOTE]
> 도메인 **필터는** 보고서 결과에 나열된 URL 도메인을 참조합니다. 

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="additional-reports-to-view"></a>볼 추가 보고서

이 문서에 설명된 보고서 외에도 다음 표에 설명된 몇 가지 다른 보고서를 사용할 수 있습니다.

****

|보고서|항목|
|---|---|
|**탐색기(Office** 365 계획 2용 Microsoft Defender) 또는 실시간 **검색(Office** 365 계획 1용 Microsoft Defender)|[위협 탐색기 (실시간 검출)](threat-explorer.md)|
|**최상위 보낸** 사람 및 받는 사람 보고서, 스푸핑 메일 보고서 및 스팸 검색 보고서와 같은 전자 메일 보안 보고서|[보안 및 준수 센터의 전자 메일 보안 보고서 보기](view-email-security-reports.md)|
|**전달 보고서,** 메일 흐름 상황 보고서, 최상위 보낸 사람 및 받는 사람 보고서 등의 메일 흐름 보고서|[보안 및 준수 센터에서 & 흐름 보고서 보기](view-mail-flow-reports.md)|
|**안전한 링크에 대한 URL** 추적(PowerShell만 해당). 이 cmdlet의 출력은 지난 7일 동안의 안전 링크 작업 결과를 보여줍니다.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**EOP 및 Office 365용 Microsoft Defender에** 대한 메일 트래픽 결과(PowerShell만 해당) 이 cmdlet의 출력에는 도메인, 날짜, 이벤트 유형, 방향, 동작 및 메시지 수에 대한 정보가 포함되어 있습니다.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**EOP 및 Office 365** 검색용 Defender에 대한 메일 세부 정보 보고서(PowerShell에만 해당) 이 cmdlet의 출력에는 전자 메일 또는 파일의 악성 파일 또는 URL, 피싱 시도, 가장 및 기타 잠재적 위협에 대한 세부 정보가 포함되어 있습니다.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Office 365용 Defender 보고서를 보는 데 필요한 사용 권한은 무엇입니까?

이 문서에 설명된 보고서를 보고 사용하려면 Security & 준수 센터에서 다음 역할 그룹 중 하나에 & 합니다.

- **조직 관리**
- **보안 관리자**
- **보안 읽기**
- **전역 읽기**

자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

**참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안  & 준수 센터의 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="what-if-the-reports-arent-showing-data"></a>보고서에 데이터가 표시되지 않는 경우 어떻게 하나요?

Office 365용 Defender 보고서에 데이터가 없는 경우 정책이 올바르게 설정되어 있지 않은지 다시 확인합니다. Office 365 보호를 위한 Defender를 설정하려면 조직에 안전한 링크 정책 및 안전 첨부 파일 정책이 정의되어 있어야 합니다. [](set-up-atp-safe-links-policies.md) [](set-up-atp-safe-attachments-policies.md) 또한 스팸 [방지 및 맬웨어 방지 보호 기능을 참조합니다.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>관련 항목

[보안 및 준수 센터의 스마트 보고서 및 인사이트](reports-and-insights-in-security-and-compliance.md)

[역할 권한(Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
