---
title: 사용자의 앱 시작커에 앱 고정
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
description: 전역 관리자는 사용자의 앱 시작 관리자에 최대 3개의 앱을 고정할 수 있습니다.
ms.openlocfilehash: 965fcbbb3f0e22074e3f6c5476d65ade98fea94c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915221"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>사용자의 앱 시작커에 앱 고정

Azure Active Directory 포털의 컨트롤을 사용하여 최대 3개의 앱을 고정하여 조직의 Office.com 사용자에 대한 앱 시작 프로그램을 만들 수 있습니다. 응용 프로그램 그룹을 구성할 수 있습니다. 나중에 추가하는 모든 앱은 사용자가 원하는 경우 이 기능을 언핑할 수 있습니다. 사용자를 위해 앱을 고정하려면 클라우드 응용 프로그램 관리자 또는 Azure Active Directory의 응용 프로그램 관리자 또는 Office 365의 전역 관리자일 수 있습니다. 관리자 역할에 대한 자세한 내용은 [Azure Active Directory의](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 관리자 역할 및 [Microsoft 365의 관리자 역할을 참조하세요.](../add-users/about-admin-roles.md) 

앱 시작 프로그램 및 앱 Office.com 자세한 내용은 [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 앱 시작 프로그램 및 업데이트 [office.com-Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 앱 시작커 블로그 문서를 참조하세요.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Azure Active Directory 포털을 사용하여 앱 고정

1. 의 Microsoft 365 관리 센터로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 이동하세요.
2. In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.
3. **Azure Active Directory에서** 엔터프라이즈 응용 **프로그램 사용자 설정을**  >  **선택합니다.**
4. Office **365 설정 섹션에서** 응용 프로그램 **추가 를 선택합니다.**
5. 사용자의 앱 시작 프로그램에 고정하려는 응용 프로그램을 선택한 다음 추가 를 **선택하십시오.**

:::image type="content" source="../../media/add-apps.png" alt-text="앱을 고정하는 Microsoft 365 설정":::

### <a name="pin-a-custom-app"></a>사용자 지정 앱 고정

> [!NOTE]
> 사용자 인터페이스는 이 기능을 사용하기 위해 추가 Azure AD 라이선스를 구입해야 하는지 나타냅니다. 자세한 내용은 [Azure Active Directory 가격을 참조하세요.](https://azure.microsoft.com/pricing/details/active-directory/)

1. **Azure Active Directory에서** 모든 응용 프로그램 **페이지의** 맨 위에 있는 엔터프라이즈 응용 프로그램 새  >   응용 **프로그램을** 선택합니다.
2. 응용 **프로그램 추가 페이지에서**  갤러리가 아닌 응용 프로그램을 선택하거나 **Azure** Active Directory의 미리 보기 버전에 있는 경우 자체 응용 프로그램 만들기를 선택합니다. 
3. 응용 프로그램의 이름을 입력한 다음 사용자 및 그룹 탭에서 사용자를 **할당합니다.**
4. 속성 **탭을** 사용하여 앱의 아이콘을 업로드합니다.
5. 앱에 URL을 할당하기 위해 **Single Sign-On** 탭에서 **연결된** URL을 선택한 다음 URL을 입력합니다.
6. **저장** 을 선택합니다.

## <a name="create-application-collections"></a>응용 프로그램 컬렉션 만들기

조직의 사용자에 대한 응용 프로그램 컬렉션을 만들 수도 있습니다. 자세한 내용은 Azure Portal의 내 앱 포털에서 컬렉션 [만들기를 참조하세요.](/azure/active-directory/manage-apps/access-panel-collections)