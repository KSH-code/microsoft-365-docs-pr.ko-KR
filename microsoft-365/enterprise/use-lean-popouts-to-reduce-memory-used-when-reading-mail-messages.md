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
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="0ff8b-103">마른 채로 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 감소</span><span class="sxs-lookup"><span data-stu-id="0ff8b-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="0ff8b-104">이 문서에서는 웹에서 메시지 다운로드 성능을 Outlook 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="0ff8b-105">이 문서는 프로젝트의 네트워크 계획 및 성능 [Office 365](./network-planning-and-performance.md) 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="0ff8b-106">전역 Office 365 관리자로서 웹에서 Outlook 구성하여 메모리를 많이 사용하는 더 작고 메모리를 많이 사용하는 특정 전자 메일 메시지 버전을 웹에서 Microsoft Edge Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="0ff8b-107">웹용 웹 응용 Outlook 구성되면 성능을 최적화하는 서버 쪽 렌더링 구성 요소가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0ff8b-108">2018년 3월 현재, IRM(정보 권한 관리)처럼 사용 권한 제한을 지정하는 메시지에는 린트 팝업을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="0ff8b-109">이러한 기능은 주 창에서 계속 작동하지만 기본 팝업에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="0ff8b-110">Outlook 추가 기능</span><span class="sxs-lookup"><span data-stu-id="0ff8b-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="0ff8b-111">비즈니스용 Skype 현재 상태</span><span class="sxs-lookup"><span data-stu-id="0ff8b-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="0ff8b-112">조직 내의 모든 사용자에 대해 린트 팝업을 Office 365</span><span class="sxs-lookup"><span data-stu-id="0ff8b-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="0ff8b-113">[커넥트 PowerShell을 Exchange Online 를 사용할 수 있습니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0ff8b-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="0ff8b-114">다음과 같이 LeanPopoutEnabled 매개 변수를 사용하여 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="0ff8b-115">예를 들어 조직의 모든 사용자에 대해 린트 팝업을 사용하도록 설정하려면 다음을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff8b-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="0ff8b-116">조직의 모든 사용자에 대해 사소한 팝업을 사용하지 않도록 설정:</span><span class="sxs-lookup"><span data-stu-id="0ff8b-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```