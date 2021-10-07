---
title: 마른 채로 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 감소
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: 이 문서에는 전자 메일에서 메시지 다운로드 성능을 향상시키는 데 필요한 정보가 포함되어 웹용 Outlook.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aaacacc0c1db418181690a5a4691bd251180d97c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188988"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>마른 채로 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 감소

이 문서에서는 메시지 다운로드 성능을 개선하기 위한 정보를 웹용 Outlook. 이 문서는 프로젝트의 네트워크 계획 및 성능 [Office 365](./network-planning-and-performance.md) 중입니다.
  
응용 **Office 365,** 전역 관리자 또는 사용자 관리자로, 웹용 Outlook 또는 앱의 특정 전자 메일 메시지 중 메모리를 많이 사용하는 더 작고 적은 버전의 특정 전자 메일 메시지를 전달하도록 Microsoft Edge 수 Internet Explorer.  서버 쪽 렌더링 구성 요소에 대해 웹용 Outlook 구성하면 성능을 최적화하는 서버 쪽 렌더링 구성 요소가 로드됩니다.
  
> [!NOTE]
> 2018년 3월 현재, IRM(정보 권한 관리)처럼 사용 권한 제한을 지정하는 메시지에는 린트 팝업을 사용할 수 없습니다.
  
이러한 기능은 주 창에서 계속 작동하지만 기본 팝업에서는 사용할 수 없습니다.
  
- Outlook 추가 기능
  
- 비즈니스용 Skype 현재 상태
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>조직 내의 모든 사용자에 대해 린트 팝업을 Office 365
  
1. [커넥트 PowerShell을 Exchange Online 를 사용할 수 있습니다.](/powershell/exchange/connect-to-exchange-online-powershell)
  
2. 다음과 같이 LeanPopoutEnabled 매개 변수를 사용하여 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet을 실행합니다.

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  예를 들어 조직의 모든 사용자에 대해 린트 팝업을 사용하도록 설정하려면 다음을 들 수 있습니다.
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  조직의 모든 사용자에 대해 사소한 팝업을 사용하지 않도록 설정:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
