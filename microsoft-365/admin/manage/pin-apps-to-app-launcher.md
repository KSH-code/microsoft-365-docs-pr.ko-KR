---
title: 사용자의 앱 시작 관리자에 앱 고정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: 전역 관리자는 최대 3 개의 앱을 사용자의 앱 시작 관리자에 게 고정할 수 있습니다.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310878"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>사용자의 앱 시작 관리자에 앱 고정

Azure Active Directory 포털의 컨트롤을 사용 하 여 Office.com에 최대 3 개의 앱을 고정 하 고 조직의 모든 사용자에 대 한 앱 시작 관리자를 고정할 수 있습니다. 응용 프로그램 그룹을 구성할 수도 있습니다. 나중에 추가 하는 앱은 사용자가 언제 든 지 고정이 가능 합니다. 사용자에 대해 앱을 고정 하려면 클라우드 응용 프로그램 관리자 이거나, Azure Active Directory의 응용 프로그램 관리자 이거나, Office 365의 전역 관리자 여야 합니다. 관리자 역할에 대 한 자세한 내용은 [Microsoft 365의](../add-users/about-admin-roles.md) [Azure Active Directory 및 관리자 역할에서 관리자 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 을 참조 하십시오. 

앱 시작 관리자 및 Office.com에 대 한 자세한 내용은 [모임 시작 관리자](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 및 [업데이트를 Office.com 및-Office 365 앱 시작 관리자](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 블로그 문서를 참조 하세요.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Azure Active Directory 포털을 사용 하 여 앱 고정

1. Microsoft 365 관리 센터 ()로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.
2. 왼쪽 탐색 창에서 **모두 표시**를 선택 하 고 **관리 센터**에서 **Azure Active Directory**를 선택 합니다.
3. **Azure Active Directory**에서 **엔터프라이즈 응용 프로그램**  >  **사용자 설정을**선택 합니다.
4. **Office 365 설정** 섹션에서 **응용 프로그램 추가**를 선택 합니다.
5. 사용자의 앱 시작 관리자에 게 고정할 응용 프로그램을 선택 하 고 **추가**를 선택 합니다.

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 앱 고정 설정":::

### <a name="pin-a-custom-app"></a>사용자 지정 앱 고정

> [!NOTE]
> 사용자 인터페이스는이 기능을 사용 하기 위해 추가 Azure AD 라이선스를 구입 해야 하는지 여부를 나타냅니다. 자세한 내용은 [Azure Active Directory 가격 책정](https://azure.microsoft.com/pricing/details/active-directory/)를 참조 하세요.

1. **Azure Active Directory**의 **Enterprise applications**  >  **모든 응용 프로그램** 페이지 위쪽에서 엔터프라이즈 응용 프로그램**새 응용 프로그램** 을 선택 합니다.
2. **응용 프로그램 추가** 페이지에서 **비 갤러리 응용 프로그램** 을 선택 하거나 미리 보기 버전의 Azure Active Directory에 있는 경우 **고유한 응용 프로그램을 만듭니다** . 
3. 응용 프로그램의 이름을 입력 하 고 사용자 **및 그룹** 탭에서 사용자를 할당 합니다.
4. **속성** 탭을 사용 하 여 앱에 대 한 아이콘을 업로드 합니다.
5. 앱에 URL을 할당 하려면 **Single sign-on** 탭에서 **연결** 됨을 선택 하 고 URL을 입력 합니다.
6. **저장**을 선택합니다.

## <a name="create-application-collections"></a>응용 프로그램 모음 만들기

조직의 사용자에 대 한 응용 프로그램 모음을 만들 수도 있습니다. 자세한 내용은 [Azure portal의 내 앱 포털에서 모음 만들기](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)를 참조 하세요.