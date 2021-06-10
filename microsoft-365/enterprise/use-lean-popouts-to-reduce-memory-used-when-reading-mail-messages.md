---
title: 마른 채로 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 감소
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: 이 문서에는 웹에서 사용할 수 있는 앱의 메시지 다운로드 성능을 향상하기 위해 Outlook 정보를 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925259"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>마른 채로 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 감소

이 문서에서는 웹에서 메시지 다운로드 성능을 Outlook 정보를 제공합니다. 이 문서는 프로젝트의 네트워크 계획 및 성능 [Office 365](./network-planning-and-performance.md) 중입니다.
  
전역 Office 365 관리자로서 웹에서 Outlook 구성하여 메모리를 많이 사용하는 더 작고 메모리를 많이 사용하는 특정 전자 메일 메시지 버전을 웹에서 Microsoft Edge Internet Explorer. 웹용 웹 응용 Outlook 구성되면 성능을 최적화하는 서버 쪽 렌더링 구성 요소가 로드됩니다.
  
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