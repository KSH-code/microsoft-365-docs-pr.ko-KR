---
title: Microsoft 365의 세션 시간 제한
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
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
description: Microsoft 365 클라이언트 앱에서 보안과 접근성의 균형을 조정하기 위해 세션 시간 제한을 사용하는 방법을 자세히 알아보습니다.
ms.openlocfilehash: 2c0a7c2633715ac23942a22858b41e83a091c46a
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769295"
---
# <a name="session-timeouts-for-microsoft-365"></a>Microsoft 365의 세션 시간 제한

세션 수명은 Microsoft 365 인증의 중요한 부분으로, 보안과 사용자에게 자격 증명을 요구하는 횟수를 균형 조정하는 데 중요한 구성 요소입니다.

## <a name="session-times-for-microsoft-365-services"></a>Microsoft 365 서비스의 세션 시간

사용자가 Microsoft 365 웹앱 또는 모바일 앱에서 인증하면 세션이 설정됩니다. 세션 기간 동안 사용자는 다시 인증할 필요가 없습니다. 세션은 사용자가 비활성 상태일 때, 브라우저 또는 탭을 닫을 때 또는 암호가 재설정된 경우와 같은 다른 이유로 인증 토큰이 만료될 때 만료될 수 있습니다. Microsoft 365 서비스에는 각 서비스의 일반적인 사용에 해당하는 서로 다른 세션 시간 제한이 있습니다.

다음 표에는 Microsoft 365 서비스의 세션 수명이 나열됩니다.

| Microsoft 365 서비스 | 세션 시간 제한 |
|:-----|:-----|
|Microsoft 365 관리 센터  <br/> |8시간마다 관리 센터에 대한 자격 증명을 제공해야 합니다.  <br/> |
|SharePoint Online  <br/> |사용자가 로그인 유지를 선택한 경우 5일 동안 **비활성입니다.** 이전 로그인에서 24시간 이상이 지난 후 사용자가 SharePoint Online에 다시 액세스하면 시간 제한 값이 5일로 다시 설정됩니다.  <br/> |
|Outlook Web App  <br/> |6시간  <br/> [Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) cmdlet에서 _ActivityBasedAuthenticationTimeoutInterval_ 매개 변수를 사용하여 이 값을 변경할 수 있습니다.  <br/> |
|Azure Active Directory  <br/> (최신 인증을 사용하는 Windows 클라이언트의 Office 및 Microsoft 365 응용 프로그램에서 사용)  <br/> | 최신 인증은 액세스 토큰 및 새로 고침 토큰을 사용하여 Azure Active Directory를 사용하여 Microsoft 365 리소스에 대한 액세스 권한을 부여합니다. 액세스 토큰은 인증에 성공한 후 제공된 JSON 웹 토큰으로, 1시간 동안 유효합니다. 수명이 더 긴 새로 고침 토큰도 제공됩니다. 액세스 토큰이 만료되면 Office 클라이언트는 유효한 새로 고침 토큰을 사용하여 새 액세스 토큰을 얻습니다. 사용자의 초기 인증이 여전히 유효한 경우 이 교환이 성공합니다.  <br/>  새로 고침 토큰은 90일 동안 유효하며, 지속적으로 사용할 경우 해지될 때까지 유효할 수 있습니다.  <br/>  새로 고침 토큰은 다음의 여러 이벤트로 무효화될 수 있습니다.  <br/>  새로 고침 토큰이 발급된 후 사용자의 암호가 변경된 경우  <br/>  관리자는 사용자가 액세스하려는 리소스에 대한 액세스를 제한하는 조건부 액세스 정책을 적용할 수 있습니다.  <br/> |
|Android, iOS 및 Windows 10용 SharePoint 및 OneDrive 모바일 앱  <br/> |액세스 토큰의 기본 수명은 1시간입니다. 새로 고침 토큰의 기본 최대 비활성 시간은 90일입니다.  <br/> [토큰 및 토큰 수명을 구성하는 방법에 대해 자세히](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> 새로 고침 토큰을 해지하기 위해 사용자의 Microsoft 365 암호를 다시 설정할 수 있습니다.  <br/> |
|Yammer Microsoft 365 Sign-In  <br/> |브라우저의 수명입니다. 사용자가 브라우저를 닫고 새 브라우저에서 Yammer 액세스하는 경우 microsoft Yammer 다시 인증합니다. 사용자가 쿠키를 캐시하는 타사 브라우저를 사용하는 경우 브라우저를 다시 열 때 다시 인증할 필요가 없습니다.  <br/> > [!NOTE]> Microsoft 365 2016을 사용하는 네트워크에만 Sign-In Yammer.           |

