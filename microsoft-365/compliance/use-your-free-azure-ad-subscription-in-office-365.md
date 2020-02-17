---
title: Office 365에서 무료 Azure Active Directory 구독 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: 조직의 Office 365 유료 구독에 포함되어 있는 Azure Active Directory에 액세스하는 방법을 알아봅니다.
ms.openlocfilehash: b8487b245001ffc73b975ed8f756b83e7093b1e7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069223"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a>Office 365에서 무료 Azure Active Directory 구독 사용

조직에 Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite 또는 기타 Microsoft 서비스에 대한 유료 구독이 있는 경우 Microsoft Azure Active Directory는 무료 구독이 제공됩니다. 사용자 및 다른 관리자는 Azure AD를 사용하여 사용자 및 그룹 계정을 만들고 관리할 수 있습니다. Azure AD를 사용하려면 Azure Portal로 이동하고 Office 365 계정을 사용하여 로그인하면 됩니다.

## <a name="before-you-begin"></a>시작하기 전에

비공개 브라우징 세션(일반 세션이 아님)을 사용하여 Azure Portal에 액세스합니다(아래 1단계). 이렇게 해야 현재 로그인된 자격 증명이 Azure로 전달되지 않습니다. Internet Explorer에서 InPrivate 브라우징 세션을 열거나 Mozilla FireFox에서 비공개 브라우징 세션을 열려면 Ctrl+Shift+P를 누르면 됩니다. Google Chrome에서 비공개 브라우징 세션(시크릿 모드 창이라고 함)을 열려면 Ctrl+Shift+N을 누릅니다.

## <a name="access-azure-active-directory"></a>Azure Active Directory에 액세스

1. [portal.azure.com](https://portal.azure.com)으로 이동한 후 Office 365 회사 또는 학생 계정으로 로그인합니다.

2. Azure Portal의 왼쪽 탐색 창에서 **Azure Active Directory**를 클릭합니다.

    ![Azure Portal의 왼쪽 탐색 창에서 Azure Active Directory를 클릭합니다.](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    **Azure Active Directory** 관리 센터가 표시됩니다.

## <a name="more-information"></a>추가 정보

- 무료 Azure Active Directory 구독에는 로그인 활동 보고서가 포함되지 않습니다. 로그인 활동(데이터 위반 시 유용할 수 있음)을 기록하려면 Azure Active Directory Premium을 구독해야 합닌다. 자세한 내용은 [Azure AD는 데이터를 얼마나 오래 저장하나요?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)를 참조하세요.

- Microsoft 365 관리 센터에서 **Azure Active Directory** 관리 센터에 액세스할 수도 있습니다. Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **관리 센터** \> **Azure Active Directory**를 클릭합니다.

- 사용자 및 그룹 관리와 기타 디렉터리 관리 작업 수행에 대한 자세한 내용은 [Azure AD 디렉터리 관리](https://docs.microsoft.com/azure/active-directory/active-directory-administer)를 참조하세요.
