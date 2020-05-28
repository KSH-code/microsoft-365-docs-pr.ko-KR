---
title: Microsoft 365 관리 센터에서 전자 메일 앱 액세스 관리
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: 사용자가 전자 메일, 일정 및 연락처에 액세스 하는 데 사용할 수 있는 모바일 앱을 선택 하는 방법을 알아봅니다.
ms.openlocfilehash: f114aa43b4bbade09d53f415aae4c5c033c20694
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400055"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 전자 메일 앱 액세스 관리

모바일 전자 메일 액세스 설정을 사용 하 여 조직의 사용자가 회사 또는 학교 계정에 액세스 하 여 전자 메일, 일정 및 연락처에 액세스 하는 데 사용할 수 있는 모바일 앱을 선택 합니다.
  
> [!IMPORTANT]
> Microsoft Intune을 사용 하 고 있거나 Exchange 관리 센터에서 모바일 장치 관리 설정을 구성한 경우가 아니면 조직에서이 설정에 액세스할 수 있습니다. 
  
## <a name="manage-email-app-options"></a>전자 메일 앱 옵션 관리

> [!IMPORTANT]
>  이 기능을 사용 하지 않는 경우에는 사용자 환경이 변경 되지 않습니다. 모든 모바일 전자 메일 앱을 사용 하 여 모바일 장치에서 전자 메일, 일정 및 연락처에 대 한 회사 또는 학교 계정에 액세스할 수 있습니다. 
    
1. 관리 센터 미리 보기에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">서비스 &amp; 추가 기능</a> 페이지로 이동합니다. 

2. **모바일 전자 메일 액세스 옵션** 페이지에서 확인란을 선택 하 고 조직의 사용자가 장치에서 전자 메일 앱을 사용 하는 방법을 선택 합니다.
  
조직의 사용자가 모바일 장치에서 회사 또는 학교 계정에 액세스 하는 방법을 설정 하는 옵션을 선택 합니다.
  
- **Outlook 전용** -조직의 사용자가 모바일 장치에서 Android 용 Outlook 또는 IOS 용 outlook을 사용 해야 합니다. 
    
- 모든 **전자 메일 앱** -조직의 모든 사용자가 Outlook을 사용 하 라는 메시지가 표시 되지만 모든 전자 메일 앱을 사용 하도록 선택할 수 있습니다. 
    
- **모든 전자 메일 앱** -조직의 새 사용자 또는 장치에서 Outlook을 사용 하 라는 메시지가 표시 되지만 모든 전자 메일 앱을 사용 하도록 선택할 수 있습니다. 
    
자세한 내용은 [모바일 장치에서 전자 메일에 액세스 하는 방법에 대 한 옵션](access-email-from-a-mobile-device.md)을 확인 하세요.
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>조직에서 새 사용자 또는 디바이스가 활성화 됨

조직의 사용자가 회사 또는 학교 전자 메일 응용 프로그램 또는 새 장치에 작업을 추가 하는 즉시 **Microsoft에서 조직의**전자 메일을 받게 됩니다. 전자 메일을 통해 Outlook 모바일 앱을 사용 하는 경우의 이점과 다운로드 위치에 대 한 링크를 제공 하는 방법을 알 수 있습니다. 그러면 사용자가 타사 앱을 계속 사용할지 여부를 선택 하거나 Outlook 모바일 앱을 사용 하도록 선택할 수 있습니다. 사용자가이 전자 메일을 처음 수신한 후 24 시간 동안 해당 장치가 격리 되 고 전자 메일, 일정 및 연락처 데이터가 업데이트 되지 않습니다. Outlook 모바일 앱을 사용 하도록 선택 하는 경우 타사 앱은 격리 된 상태로 유지 되 고 데이터는 Outlook 모바일 앱과만 동기화 됩니다. 타사 앱 사용을 계속 하기로 결정 하면 데이터가 즉시 동기화 되기 시작 합니다. 처음 24 시간 동안 작업을 수행 하지 않으면 전자 메일이 받은 편지함에서 제거 되 고 데이터가 서버에서 자동으로 동기화 되기 시작 합니다.
  
## <a name="previously-configured-users-in-your-organization"></a>조직에서 이전에 구성 된 사용자

조직의 모든 사용자에 대해 Outlook을 추천 하는 경우, 이전에 새 사용자를 위해 회사 또는 학교 전자 메일 계정을 타사 앱에 연결 하는 사용자는이 설정에 따라 48 시간 내에 **조직을 대신** 하 여 Microsoft 로부터 전자 메일을 받을 수 있습니다. 전자 메일을 통해 Outlook 모바일 앱을 사용 하는 경우의 이점과 다운로드 위치에 대 한 링크를 제공 하는 방법을 알 수 있습니다. 그러면 사용자가 타사 앱을 계속 사용할지 여부를 선택 하거나 Outlook 모바일 앱을 사용 하도록 선택할 수 있습니다. 사용자가이 전자 메일을 처음 수신한 후 24 시간 동안 해당 장치가 격리 되 고 전자 메일, 일정 및 연락처 데이터가 업데이트 되지 않습니다. Outlook 모바일 앱을 사용 하도록 선택 하는 경우 타사 앱은 격리 된 상태로 유지 되 고 데이터는 Outlook 모바일 앱과만 동기화 됩니다. 타사 앱 사용을 계속 하기로 결정 하면 데이터가 즉시 동기화 되기 시작 합니다. 처음 24 시간 동안 작업을 수행 하지 않으면 전자 메일이 받은 편지함에서 제거 되 고 데이터가 서버에서 자동으로 동기화 되기 시작 합니다. 
  

