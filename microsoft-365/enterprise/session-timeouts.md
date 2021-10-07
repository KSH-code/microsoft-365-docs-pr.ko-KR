---
title: Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: 세션 시간 제한을 사용하여 클라이언트 앱의 보안과 접근성의 균형을 Microsoft 365 방법을 알아보습니다.
ms.openlocfilehash: f5b7c87cabfd6f80061c2795568cd53955caa10f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213268"
---
# <a name="session-timeouts-for-microsoft-365"></a>Microsoft 365

세션 수명은 Microsoft 365 인증의 중요한 부분으로, 보안과 사용자에게 자격 증명을 요구하는 횟수를 균형적으로 조정하는 데 중요한 구성 요소입니다.

## <a name="session-times-for-microsoft-365-services"></a>Microsoft 365 세션 시간

사용자가 웹앱 또는 모바일 앱에서 Microsoft 365 인증하면 세션이 설정됩니다. 세션 기간 동안 사용자는 다시 인증할 필요가 없습니다. 세션은 사용자가 비활성 상태일 때, 브라우저 또는 탭을 닫을 때 또는 암호가 재설정된 경우와 같은 다른 이유로 인증 토큰이 만료될 때 만료될 수 있습니다. Microsoft 365 서비스마다 일반적인 사용에 해당하는 서로 다른 세션 시간 제한이 있습니다.

다음 표에는 Microsoft 365 세션 수명이 나열되어 있습니다.

| Microsoft 365 서비스 | 세션 시간 제한 |
|:-----|:-----|
|Microsoft 365 관리 센터  <br/> |8시간마다 관리 센터에 대한 자격 증명을 제공해야 합니다.  <br/> |
|SharePoint Online  <br/> |사용자가 로그인 유지를 선택한 경우 5일 동안 **비활성으로 유지됩니다.** 사용자가 이전 로그인에서 24시간 SharePoint 후에 다시 온라인에 액세스하면 시간 제한 값이 5일로 다시 설정됩니다.  <br/> |
|Outlook Web App  <br/> |6시간.  <br/> [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet의 _ActivityBasedAuthenticationTimeoutInterval_ 매개 변수를 사용하여 이 값을 변경할 수 있습니다.  <br/> |
|Azure Active Directory  <br/> (최신 인증을 사용하는 Office Microsoft 365 클라이언트의 Windows 응용 프로그램에서 사용)  <br/> | 최신 인증은 액세스 토큰 및 새로 고침 토큰을 사용하여 Microsoft 365 리소스에 대한 액세스 권한을 Azure Active Directory. 액세스 토큰은 인증 성공 후 제공된 JSON 웹 토큰으로, 1시간 동안 유효합니다. 수명이 더 긴 새로 고침 토큰도 제공됩니다. 액세스 토큰이 만료되면 Office 클라이언트가 유효한 새로 고침 토큰을 사용하여 새 액세스 토큰을 얻습니다. 사용자의 초기 인증이 여전히 유효한 경우 이 교환이 성공합니다.  <br/>  새로 고침 토큰은 90일 동안 유효하며, 지속적으로 사용할 경우 해지될 때까지 유효할 수 있습니다.  <br/>  새로 고침 토큰은 다음과 같은 여러 이벤트로 무효화될 수 있습니다.  <br/>  새로 고침 토큰이 발급된 후 사용자의 암호가 변경된 경우  <br/>  관리자는 사용자가 액세스하려는 리소스에 대한 액세스를 제한하는 조건부 액세스 정책을 적용할 수 있습니다.  <br/> |
|SharePoint, iOS OneDrive 및 앱용 모바일 앱을 Windows 10  <br/> |액세스 토큰의 기본 수명은 1시간입니다. 새로 고침 토큰의 기본 최대 비활성 시간은 90일입니다.  <br/> [토큰 및 토큰 수명을 구성하는 방법에 대해 자세히 알아보시고](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> 새로 고침 토큰을 해지하기 위해 사용자의 암호를 다시 Microsoft 365 있습니다.  <br/> |
|Yammer Microsoft 365 Sign-In  <br/> |브라우저의 수명입니다. 사용자가 브라우저를 닫고 새 Yammer 액세스하는 경우 Yammer 다시 인증을 Microsoft 365. 사용자가 쿠키를 캐시하는 타사 브라우저를 사용하는 경우 브라우저를 다시 열 때 다시 인증할 필요가 없습니다.  <br/> > [!NOTE]> 이 사용은 네트워크에서 Microsoft 365 Sign-In 사용할 Yammer.           |