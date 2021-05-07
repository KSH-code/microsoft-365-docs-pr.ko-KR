---
title: 이전 직원 제거 - 개요
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 이 솔루션의 단계에 따라 이전 직원을 제거하고 Microsoft 365 데이터를 보호합니다.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241739"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>개요: 이전 직원 및 보안 데이터 제거

자주 묻는 질문은 "직원이 퇴사할 때 데이터를 보호하고 액세스를 보호하기 위해 어떻게 해야 나요?"입니다. 이 문서 시리즈에서는 사용자 Microsoft 365 차단하는 방법, 데이터를 보호하기 위해 취해야 하는 단계 및 다른 직원이 데이터에 액세스할 수 있도록 허용하는 방법에 대해 설명했습니다.

직원 제거에 대한 짧은 비디오를 시청합니다. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](../../business-video/index.yml)를 참조하세요.

직원이 로그인하지 못하게 방지:

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 사용자 이름 옆의 상자를 선택한 다음 암호 다시 설정을 **선택합니다.**
3. 새 암호를 입력한 다음 다시 설정을 **선택합니다.** (보내지 않습니다.)
4. 사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 로그인 시작 **을 선택합니다.** 

> [!NOTE]
> 전역 관리자가 로그인을 시작해야 합니다.

1시간 이내에 또는 현재 Microsoft 365 페이지에서 나면 다시 로그인하라는 메시지가 표시됩니다. 액세스 토큰은 한 시간 동안 양호하기 때문에 시간 표시 막대는 해당 토큰에 남아 있는 시간 및 현재 웹 페이지를 탐색하는지 여부에 따라 결정됩니다.

> [!IMPORTANT]
> 이 솔루션의 단계에 번호를 매기며 정확한 순서를 사용하여 솔루션을 완료할 것은 아니어도 됩니다. 이러한 방식으로 단계를 수행해보는 것이 좋습니다.

## <a name="before-you-begin"></a>시작하기 전에

이 솔루션의 단계를 완료하려면 전역 관리자로 설정해야 합니다.

|||
|:-----|:-----|
|**단계** <br/> |**이렇게 하는 이유** <br/> |
|[1단계 - 이전 직원이 로그인하지 못하게 방지하고 Microsoft 365 액세스 차단](remove-former-employee-step-1.md) <br/> |이렇게 하면 이전 직원이 로그인하지 못하고 Microsoft 365 액세스하지 못하게 Microsoft 365 있습니다. <br/> |
|[2단계 - 이전 직원 사서함의 내용 저장](remove-former-employee-step-2.md) <br/> |이 기능은 직원의 작업을 인계할 사람이나 소송이 있는 경우 유용합니다. <br/> |
|[3단계 - 이전 직원의 전자 메일을 다른 직원에게 전달하거나 공유 사서함으로 변환](remove-former-employee-step-3.md) <br/> |이렇게 하면 이전 직원의 전자 메일 주소를 활성 상태로 유지할 수 있습니다. 이전 직원의 주소로 여전히 전자 메일을 보내는 고객 또는 파트너가 있는 경우 업무를 인수하는 사람에게 전자 메일이 전달됩니다. <br/> |
|[4단계 - 다른 직원에게 데이터 및 OneDrive 액세스 Outlook 부여](remove-former-employee-step-6.md) <br/> |사용자의 라이선스만 제거하고 계정을 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다. <br/><br/> 계정을 삭제하기 전에 해당 계정에 대한 액세스 권한을 OneDrive Outlook 합니다. 직원의 계정을 삭제하면 해당 계정 및 OneDrive Outlook **30일** 동안 보존됩니다. 그러나 해당 30일 동안 사용자 계정을 복원하고 해당 콘텐츠에 액세스할 수 있습니다. 사용자 계정을 복원하면 30일이 OneDrive Outlook 콘텐츠에 계속 액세스할 수 있습니다. <br/> |
|[5단계 - 이전 직원의 모바일 장치 지우기 및 차단](remove-former-employee-step-4.md) <br/> |휴대폰 또는 태블릿에서 비즈니스 데이터를 제거합니다.  <br/> |
|[6단계 - 이전 직원의 Microsoft 365 라이선스 제거 및 삭제](remove-former-employee-step-7.md) <br/> |라이선스를 제거하면 다른 사람에게 해당 라이선스를 할당할 수 있습니다. 또는 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않도록 라이선스를 삭제할 수 있습니다.  <br/><br/> 라이선스를 제거하거나 삭제하면 사용자의 이전 전자 메일, 연락처 및 일정이 **30일** 간 보존된 후 영구적으로 삭제됩니다. 라이선스를 제거하거나 삭제하되 계정은 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  <br/> |
|[7단계 - 이전 직원의 사용자 계정 삭제](remove-former-employee-step-7.md) <br/> |그러면 관리 센터에서 계정이 제거됩니다. 깔끔하게 정리됩니다. <br/> |

## <a name="related-articles"></a>관련 문서

[사용자 복원](restore-user.md)
