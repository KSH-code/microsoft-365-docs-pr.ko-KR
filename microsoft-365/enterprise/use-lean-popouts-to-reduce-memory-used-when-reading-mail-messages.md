---
title: 마른 채우기 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 감소
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
description: 이 문서에는 웹용 Outlook에서 메시지 다운로드 성능을 향상시키는 데 필요한 정보가 포함되어 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692778"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>마른 채우기 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 감소

이 문서에는 웹용 Outlook에서 메시지 다운로드 성능을 개선하기 위한 정보가 포함되어 있습니다. 이 문서는 [Office 365](https://aka.ms/tune) 프로젝트에 대한 네트워크 계획 및 성능 조정의 일부입니다.
  
Office 365 전역 관리자는 Microsoft Edge 또는 Microsoft Edge에서 메모리를 많이 사용하는 더 작고 메모리를 많이 사용하는 특정 전자 메일 메시지 버전을 제공하도록 웹용 Outlook을 구성할 수 Internet Explorer. 웹용 Outlook에 대해 희미한 팝업이 구성되면 성능을 최적화하는 서버 쪽 렌더링 구성 요소가 로드됩니다.
  
> [!NOTE]
> 2018년 3월 현재, IRM(정보 권한 관리)처럼 사용 권한 제한을 지정하는 메시지에는 마른 채로 팝업을 사용할 수 없습니다.
  
이러한 기능은 주 창에서 계속 작동하지만 기본 팝업에서는 사용할 수 없습니다.
  
- Outlook 추가 기능
  
- 비즈니스용 Skype 현재 상태
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Office 365 조직 내의 모든 사용자에 대해 원하지 않은 팝업을 구성합니다.
  
1. [원격 PowerShell을 사용하여 Exchange Online에 연결합니다.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx )
  
2. 다음과 같이 LeanPopoutEnabled 매개 변수를 사용하여 [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet을 실행합니다.

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  예를 들어 조직의 모든 사용자에 대해 린트 팝업을 사용하도록 설정하려면
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  조직의 모든 사용자에 대해 마른 채우기 팝업을 사용하지 않도록 설정:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
