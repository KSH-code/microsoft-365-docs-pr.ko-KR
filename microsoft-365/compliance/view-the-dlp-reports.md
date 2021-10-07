---
title: 데이터 손실 방지에 대한 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 정책의 DLP Office 365 DLP 정책 일치, 재지정 또는 가짓 긍정 수를 보고 시간이 경과에 따라 추세인지 또는 하락 추세인지를 볼 수 있습니다.
ms.openlocfilehash: c585d65a9ce91ca0fae3881efc107efdd4537889
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198580"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>데이터 손실 방지에 대한 보고서 보기

DLP(데이터 손실 방지) 정책을 만든 후 의도한 것만큼 작동하고 규정 준수를 유지하도록 도와주는지 확인할 수 있습니다. 보안 및 준수 센터의 DLP 보고서를 사용하면 &amp; 다음을 빠르게 볼 수 있습니다.
  
- **DLP 정책 일치** 이 보고서에는 시간이 지날 때 일치하는 DLP 정책의 수가 표시 됩니다. 날짜, 위치, 정책 또는 작업을 통해 보고서를 필터링할 수 있습니다. 이 보고서를 사용하여 다음 작업을 수행할 수 있습니다. 
    
  - 테스트 모드에서 실행할 때 DLP 정책을 조정하거나 구체화합니다. 콘텐츠와 일치하는 특정 규칙을 볼 수 있습니다.
    
  - 특정 기간에 초점을 맞추고 스파이크 및 추세의 이유를 이해합니다.
    
  - 조직의 DLP 정책을 위반하는 비즈니스 프로세스를 검색합니다.
    
  - 콘텐츠에 적용되는 작업을 확인하여 DLP 정책이 비즈니스에 미치는 영향을 파악합니다.
    
  - 해당 정책과 일치하는 항목을 표시하여 특정 DLP 정책의 준수를 확인합니다.
    
  - 조직의 인시던트에 기여하는 상위 사용자 및 반복 사용자 목록을 봅니다.
    
  - 조직에서 중요한 정보의 상위 유형 목록을 봅니다.
    
- **DLP 인시던트** 또한 이 보고서에는 정책 일치 보고서와 같이 시간이 지날 때의 정책 일치도 표시 됩니다. 그러나 정책 일치 보고서에는 규칙 수준에서 일치하는 일치가 표시 됩니다. 예를 들어 전자 메일이 세 가지 다른 규칙과 일치하는 경우 정책 일치 보고서에는 세 개의 서로 다른 행 항목이 표시 됩니다. 반면 인시던트 보고서에는 항목 수준에서 일치하는 항목이 표시됩니다. 예를 들어 전자 메일이 세 가지 다른 규칙과 일치하는 경우 인시던트 보고서에는 해당 콘텐츠에 대한 단일 행 항목이 표시됩니다. 
    
  보고서 수는 다르게 집계하기 때문에 특정 규칙과 일치하는 일치를 식별하고 DLP 정책을 미세 조정하는 데 정책 일치 보고서가 더 좋습니다. 인시던트 보고서는 DLP 정책에 문제가 되는 특정 콘텐츠를 식별하는 데 더 적합합니다.
    
- **DLP 가긍성** 및 다시 시정 DLP 정책에서 사용자가 정책을 다시 설정하거나 가짓 긍정을 보고할 수 있도록 허용하는 경우 이 보고서에는 시간이 지날 때 이러한 인스턴스의 수가 표시될 수 있습니다. 날짜, 위치 또는 정책별로 보고서를 필터링할 수 있습니다. 이 보고서를 사용하여 다음 작업을 수행할 수 있습니다. 
    
  - 가양성 오류가 많이 발생하는 정책을 확인하여 DLP 정책을 조정하거나 조정합니다.
    
  - 정책을 재정의하여 정책 팁을 해결할 때 사용자가 제출한 사유를 확인합니다.
    
  - 많은 수의 사용자 재정의를 발생시켜 DLP 정책이 유효한 비즈니스 프로세스와 충돌하는 위치를 검색합니다.
    
모든 DLP 보고서에는 최근 4개월 동안의 데이터가 표시될 수 있습니다. 최신 데이터가 보고서에 표시되는 데 최대 24시간이 걸릴 수 있습니다.
  
이러한 보고서는 보안 및 준수 센터 보고서 대시보드 &amp; \> **에서 찾을 수** \> **있습니다.**
  
![DLP 정책은 보고서와 일치합니다.](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>사용자가 제출한 정당성에 대한 검토

DLP 정책에서 사용자가 이를 재정의할 수 있도록 허용하는 경우 가양성 및 재정의 보고서를 사용하여 정책 팁에서 사용자가 제출한 텍스트를 볼 수 있습니다.
  
![DLP 가 긍정 및 긍정 보고서에 대한 세부 정보의 사소한 필드입니다.](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>인사이트 및 권장 사항에 대한 조치 수행

보고서에는 빨간색 경고 아이콘을 클릭하여 잠재적인 문제에 대한 세부 정보를 보고 가능한 수정 조치를 취할 수 있는 인사이트 및 권장 사항이 표시됩니다.
  
![인사이트 아이콘을 클릭하여 수행할 세부 정보 및 작업을 볼 수 있습니다.](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>DLP 보고서에 대한 사용 권한

보안 및 준수 센터에서 DLP 보고서를 & 다음을 할당해야 합니다.

- **Exchange** 관리 센터의 보안 읽기 Exchange. 기본적으로 이 역할은 조직 관리 센터의 조직 관리 및 보안 읽기 Exchange 할당됩니다.

- **보안 및 준수** 센터의 보기 전용 DLP 준수 &. 기본적으로 이 역할은 보안 및 준수 센터의 준수 관리자, 조직 관리, 보안 관리자 및 보안 읽기 권한자 & 할당됩니다.

- **보기 전용 관리자** 센터에서 받는 Exchange 역할입니다. 기본적으로 이 역할은 View-Only 관리 센터의 조직 관리 역할 Exchange 할당됩니다.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>DLP 보고서의 cmdlet 찾기

대부분의 보안 &amp; 준수 센터용 cmdlet을 사용하려면 다음의 단계를 따르십시오:
  
1. [커넥트 PowerShell을 사용하여 보안 및 준수 &amp; 센터에 연결](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. 다음 보안 및 준수 센터 [ &amp; cmdlet 사용](/powershell/exchange/exchange-online-powershell)
    
하지만 DLP 보고서에서는 Exchange Online을 포함한 Office 365에서 데이터를 가져와야 합니다. 이러한 이유로 DLP 보고서에 대한 cmdlet은 보안 및 준수 센터 powershell이 Exchange Online &amp; Powershell에서 사용할 수 있습니다. 따라서 DLP 보고서용 cmdlet을 사용하려면 다음의 단계가 필요합니다:
  
1. [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. 다음과 같은 DLP 보고서용 cmdlet 중 하나 사용
    
      - [Get-DlpDetectionsReport](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [Get-DlpDetailReport](/powershell/module/exchange/get-dlpdetailreport)
