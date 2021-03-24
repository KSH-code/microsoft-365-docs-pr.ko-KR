---
title: Microsoft 365 Enterprise 서비스 및 응용 프로그램 구성
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: deployment
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 7cec08a5-97fd-4761-b23b-ef3d66519e30
f1.keywords:
- NOCSH
description: SharePoint, Exchange 및 비즈니스용 Skype와 같은 Microsoft 365 Enterprise 서비스 및 응용 프로그램을 구성합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ab05267b88528709335aff9c02f4080aaca12bb4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051511"
---
# <a name="configure-microsoft-365-enterprise-services-and-applications"></a>Microsoft 365 Enterprise 서비스 및 응용 프로그램 구성

기본 [설정 지침은](../admin/setup/setup.md) 가능한 한 짧은 시간에 모든 사람이 Microsoft 365 서비스 및 응용 프로그램을 사용할 수 있도록 하는 데 도움이 됩니다. 경우에 따라 모든 사용자가 사용을 시작하기 전에 구성하는 것이 좋은 경우도 있습니다. 예를 들어 메일 라우팅, 파일 저장소 또는 공유 정책을 구성하려는 경우를 예로 들 수 있습니다. 
  
Microsoft 365를 설정하는 데 도움이 필요하면 **[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)** 또는 [Microsoft 365 및 Office 365](setup-guides-for-microsoft-365.md)서비스에 대한 설치 가이드를 사용하세요.
  
|**서비스 및 응용 프로그램**|**리소스**|
|:-----|:-----|
|**Microsoft 365 Suite** |- [Microsoft 365 로그인 페이지에 회사 브랜드 추가](https://support.office.com/article/Add-your-company-branding-to-Office-365-Sign-In-Page-a1229cdb-ce19-4da5-90c7-2b9b146aef0a) <br> - [Microsoft 365 도움말 창에 사용자 지정된 지원 센터 정보 추가](https://support.office.com/article/Add-customized-help-desk-info-to-the-Office-365-help-pane-9dd9b104-68f7-4d49-9a30-82561c7d79a3) <br> - [Microsoft Azure AD와 다른 응용 프로그램의 통합 추가](https://support.office.com/article/Integrated-Apps-and-Azure-AD-for-Office-365-administrators-cb2250e3-451e-416f-bf4e-363549652c2a).  <br> 그룹을 사용하여 전자 메일, 일정, 문서 및 채팅으로 공동 작업하는 방법에 대해 - [자세히 알아보기](https://support.office.com/Article/Learn-more-about-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) <br> - [Microsoft 365에서 모바일 장치 관리 활성화 및 사용](https://support.office.microsoft.com/article/Manage-mobile-devices-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd) <br> - [Microsoft 365 연결 모니터링](monitor-connectivity.md) |
|**전자 메일** <br> (Exchange Online) | - [Exchange 배포 도우미를 사용하여 Exchange Hybrid](https://technet.microsoft.com/exdeploy2013)로 마이그레이션할 준비 하기  <br> - [Exchange 마이그레이션 관리자](https://aka.ms/office365setup)를 사용하여 사용자 지정 설치 지침 확인  <br> - [Exchange Online Protection 설정](../security/defender-365-security/set-up-your-eop-service.md) |
|**사이트** <br> (SharePoint Online) | -SharePoint Server [2013에](/SharePoint/hybrid/hybrid) 대한 하이브리드 기능 구성<br> - [사이트 서식 파일을 만들고 사용](https://support.office.com/article/Create-and-use-site-templates-60371B0F-00E0-4C49-A844-34759EBDD989)하여 SharePoint Online의 모양과 느낌을 사용자 지정 <br> - [SharePoint Online 계획 가이드](https://support.office.com/article/SharePoint-Online-Planning-Guide-for-Office-365-for-business-d5089cdf-3fd2-4230-acbd-20ecda2f9bb8) 또는 [ SharePoint Online 배포 관리자](https://aka.ms/spoguidance)를 사용하여 추가 기능 계획 및 구성 <br> - 비디오 포털 [관리](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da) |
|**IM 및 온라인 모임** <br> (비즈니스용 Skype Online) | - [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid) 또는 비즈니스용 [Skype 2015에](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 대한 하이브리드 기능 구성<br> - [비즈니스용 Skype Online 설정](https://support.office.com/article/Set-up-Skype-for-Business-Online-40296968-e779-4259-980b-c2de1c044c6e) 및 통화 라우팅, 전화 회의 및 공유와 같은 공통 기능 구성  <br> - [비즈니스용 Skype 배포 관리자](/MicrosoftTeams/faq-journey)를 사용하여 사용자 지정된 설정 지침 확인 |
| **파일 저장소 및 공유** <br> (비즈니스용 OneDrive 및 SharePoint Online) | - [Microsoft 365](https://support.office.com/article/7aa9cdc8-2245-4218-81ee-86fa7c35f1de#BKMK_WhatDif)파일 저장 및 공유 설정: 비즈니스용 OneDrive를 사용하여 파일을 저장해야 하는 경우 및 ShharePoint Online 팀 사이트를 사용해야 하는 경우를 배워야 합니다. <br> - [파일 저장 및](https://support.office.com/article/7aa9cdc8-2245-4218-81ee-86fa7c35f1de#BKMK_MoveDocsVideo)공유 설정: 비즈니스용 OneDrive 및 SharePoint 팀 사이트에서 파일을 업로드하는 것이 얼마나 쉬운지 확인 <br> - [파일 저장 및](https://support.office.com/article/7aa9cdc8-2245-4218-81ee-86fa7c35f1de#BKMK_Store)공유 설정: 비즈니스용 OneDrive 및 팀 사이트에 파일을 업로드하는 모든 단계를 수행합니다. 파일 공유에 대한 팁 학습 <br> - [비즈니스용 OneDrive 설정 가이드 ](https://aka.ms/OD4Bguidance)를 사용하여 사용자 지정된 지침 확인 |
|**Microsoft 365 응용 프로그램** | - Microsoft 365 관리자는 [Office](/deployoffice) 배포 가이드를 사용하여 엔터프라이즈용 Microsoft 365 앱 배포 또는 업그레이드를 계획하는 데 도움을 받을 수 있습니다.  <br> - [Microsoft 365 관리 센터용 Power BI](https://support.office.com/article/Power-BI-for-Office-365-Admin-Center-Help-5e391ecb-500c-47a3-bd0f-a6173b541044) <br> - [Microsoft 365 관리자용 Office Delve](https://support.office.com/article/Office-Delve-for-Office-365-admins-54f87a42-15a4-44b4-9df0-d36287d9531b) <br> - [Sway에 대한 질문과 대답(FAQ)](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075) <br> - [Project Online 시작](https://support.office.com/article/Get-started-with-Project-Online-e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)  <br> - [Microsoft Intune 배포 관리자](/mem/intune/) |
|**기업용 소셜** <br> (Yammer) | - [Microsoft Yammer 사용](https://support.office.com/article/Plan-for-Yammer-integration-with-Office-365-4086681f-6de1-4d39-aa72-752b2af1cbd7)  <br> - [Yammer Enterprise 설정 가이드](https://aka.ms/yammerdeploy)를 사용하여 사용자 지정된 설정 확인 |