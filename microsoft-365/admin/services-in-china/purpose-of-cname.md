---
title: MSOID용 Office 365 CNAME 레코드의 용도
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 인증 프로세스에 가장 적합한 서버로 연결되는 Office 365의 'MSOID' CNAME 레코드에 대해 자세히 알아보면 응답 속도가 더 빨라집니다.
monikerRange: o365-21vianet
ms.openlocfilehash: aea04391768993c40978d94b50817244cd77405c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655487"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>MSOID용 Office 365 CNAME 레코드의 용도

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
> [!NOTE]
> 다음은 21Vianet에서 운영하는 **Office 365에만 적용됩니다.
  
Office 365에서 "MSOID" CNAME 레코드를 추가해야 하는 이유가 궁금할 수 있습니다. 이 레코드는 사용하는 구독에 상관없이 모든 사용자 지정 도메인에 대해 추가해야 하는 레코드입니다. CNAME 레코드가 필요한 이유는 무엇인가요? 약간 기술적이지만 필수적인 요소로, 특정 인증 프로세스를 위해 최상의 서버로 연결시켜 주기 때문에 보다 빠르게 응답을 얻을 수 있습니다.
  
기술 세부 사항: 비즈니스용 Skype Online, Outlook, Windows PowerShell 또는 Microsoft Azure Active Directory 동기화 도구 등 Office 365와 연동되는 클라이언트 응용 프로그램을 실행하는 경우 자격 증명이 인증되어 있어야 합니다. Office 365는 CNAME 레코드를 사용하여 사용자 위치의 정확한 인증 끝점을 가리키므로 빠른 인증 응답 시간이 보장됩니다.
  
CNAME 레코드가 도메인에서 누락된 경우 이 응용 프로그램은 미국에 있는 기본 인증 끝점을 사용하며, 이에 따라 인증 속도가 느릴 수 있습니다. **대상 주소** 에 오타가 있는 경우와 같이 이 CNAME 레코드가 적절하게 구성되지 않은 경우, 이 응용 프로그램은 인증할 수 없습니다.
  
 **Office 365에서 도메인의 DNS** 레코드를 관리하는 경우 Office 365에서 이 CNAME 레코드를 설정합니다. 
  
 **DNS 호스트에서** 도메인의 DNS 레코드를 관리하는 경우 DNS 호스트에 대한 지침에 따라 이 레코드를 [직접 만드세요.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)
  
Office 365 배포를 계획하고 있으며 추가 또는 업데이트해야 할 수 있는 모든 DNS 레코드에 대한 자세한 내용을 확인하려면 [참조: Office 365용 외부](https://go.microsoft.com/fwlink/?LinkId=579013)도메인 이름 시스템 레코드에서 해당 레코드에 대해 읽어야 합니다.
  

