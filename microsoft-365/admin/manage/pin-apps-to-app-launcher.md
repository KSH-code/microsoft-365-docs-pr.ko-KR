---
title: 사용자의 앱 시작커에 앱 고정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
- Adm_TOC
ms.service: o365-administration
ms.custom: admindeeplinkMAC
localization_priority: Normal
description: 전역 관리자는 사용자의 앱 시작 관리자에 최대 3개의 앱을 고정할 수 있습니다.
ms.openlocfilehash: 7e9975b13f66f39abd61a238cb30463baa9ed34e
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59933366"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>사용자의 앱 시작커에 앱 고정

Azure Active Directory 포털의 컨트롤을 사용하여 최대 3개의 앱을 Office.com에 고정하고 조직의 모든 사용자에 대한 앱 시작 프로그램을 고정할 수 있습니다. 응용 프로그램 그룹을 구성할 수 있습니다. 나중에 추가하는 모든 앱은 사용자가 원하는 경우 이 기능을 언핑할 수 있습니다. 사용자를 위해 앱을 고정하려면 조직의 클라우드 응용 프로그램 관리자 또는 Azure Active Directory 전역 관리자 또는 Office 365. 관리자 역할에 대한 자세한 내용은 에서 [Azure AD](/azure/active-directory/roles/permissions-reference) 기본 제공 역할 및 관리자 [역할을 Microsoft 365.](../add-users/about-admin-roles.md) 

앱 시작 프로그램 및 Office.com에 대한 자세한 [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 내용은 앱 시작 office.com 업데이트 및 앱 시작 Office 365 [문서를](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 참조하세요.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>앱 Azure Active Directory 사용하여 앱 고정

1. 의 Microsoft 365 관리 센터 로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>
2. In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory.**
3. 에서 **Azure Active Directory** 응용 **Enterprise 사용자**  >  **설정을 선택합니다.**
4. In the **Office 365 설정** section, choose **Add application**.
5. 사용자의 앱 시작 프로그램에 고정하려는 응용 프로그램을 선택한 다음 추가 를 **선택하십시오.**

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 설정을 사용하여 앱을 고정합니다.":::

### <a name="pin-a-custom-app"></a>사용자 지정 앱 고정

> [!NOTE]
> 사용자 인터페이스는 이 기능을 사용하기 위해 추가 Azure AD 라이선스를 구입해야 하는지 나타냅니다. 자세한 내용은 가격 [Azure Active Directory 참조하세요.](https://azure.microsoft.com/pricing/details/active-directory/)

1. In **Azure Active Directory**, choose **Enterprise Applications** New  >  **application** on the top of the All **applications** page.
2. 응용 **프로그램 추가 페이지에서**  갤러리가 아닌 응용  프로그램을 선택하거나 미리 보기 버전의 응용 프로그램에 있는 경우 자체 응용 프로그램 Azure Active Directory. 
3. 응용 프로그램의 이름을 입력한 다음 사용자 및 그룹 탭에서 사용자를 **할당합니다.**
4. 속성 **탭을** 사용하여 앱의 아이콘을 업로드합니다.
5. 앱에 URL을 할당하기 위해 **Single Sign-On** 탭에서 **연결된** URL을 선택한 다음 URL을 입력합니다.
6. **저장** 을 선택합니다.

## <a name="create-application-collections"></a>응용 프로그램 컬렉션 만들기

조직의 사용자에 대한 응용 프로그램 컬렉션을 만들 수도 있습니다. 자세한 내용은 Azure Portal의 내 앱 포털에서 컬렉션 [만들기를 참조하세요.](/azure/active-directory/manage-apps/access-panel-collections)