---
title: 사용 Microsoft 365 문제 해결
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 사용 현황 분석 템플릿 앱의 문제를 Microsoft 365 방법을 알아보십시오.
ms.openlocfilehash: b13ec0338c6ad48a5f5006528d77fbbdc290e7f5
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774355"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>사용 Microsoft 365 문제 해결

다음 오류 메시지 목록을 살펴보고 사용 현황 분석과 관련한 가장 일반적인 문제에 대한 Microsoft 365 살펴보십시오.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>요청을 처리할 수 없습니다. 이 데이터는 먼저 사용자 센터에서 구독해야 Microsoft 365 관리 센터

 **오류 코드:** 422 
  
 **이 메시지가 표시될 위치:** 이 Power BI 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 Microsoft 365 있습니다. 
  
 **원인:** 앱에 연결하기 전에 앱의 데이터를 구독해야 Microsoft 365 관리 센터. 이 단계를 먼저 수행하지 않은 경우 테넌트 ID를 제공한 경우에도 템플릿 앱에 연결할 Microsoft 365 없습니다. 
  
 **이 오류를 해결합니다.** 데이터를 구독하려면 관리 센터 보고서 사용 현황으로 이동하여 주 대시보드 페이지에서 Microsoft 365 사용 현황 분석 타일을 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> 찾습니다. 시작 **단추를** 선택한 다음 열  수 있는 보고서 창에서 데이터 사용 현황 분석에서 사용 **현황 Microsoft 365** 사용 현황 Power BI 켜기 및 저장을 **선택합니다.**
  
## <a name="we-are-processing-your-data"></a>데이터를 처리하고 있습니다.

 **이 메시지가 표시될 위치:** 웹 **Microsoft 365** 대시보드의 사용 현황 분석 타일에서 Microsoft 365 관리 센터.  
  
 **원인:** 앱의 [](enable-usage-analytics.md) 템플릿 앱에서 데이터를 보게 Microsoft 365 관리 센터 경우 Microsoft 365 시스템에서 조직의 이전 사용 현황 데이터를 생성하기 시작합니다. 테넌트의 크기에 따라 이 단계는 2시간에서 48시간까지 걸릴 수 있습니다. 
  
 **이 문제를 해결합니다.** 잠시 기다렸다가 메시지가 3일  후에 데이터로 변경되지 않는 경우 비즈니스 지원을 Microsoft 365 [문의합니다.](../../business-video/get-help-support.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>현재 요청을 처리할 수 없습니다. 아직 조직의 데이터를 준비하고 있습니다.

 **오류 코드:** 423 
  
 **이 메시지가 표시될 위치:** Power BI 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 Microsoft 365 있습니다. 
  
 **원인:** 관리 [센터에서](enable-usage-analytics.md) 템플릿 앱의 데이터를 보게 옵트인하면 Microsoft 365 조직의 이전 사용 현황 데이터가 생성됩니다. 테넌트의 크기에 따라 이 단계는 2시간에서 48시간까지 걸릴 수 있습니다. 
  
 **이 문제를 해결합니다.** 유의하시기 바랍니다. 그러나 메시지가 시작된 후 3일이라도 데이터가 준비되었습니다로 변경되지 않는 경우 비즈니스 지원을 Microsoft 365 [문의합니다.](../../business-video/get-help-support.md) 
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>입력하신 테넌트 ID의 형식이 올바르지 않습니다.

 **오류 코드:** 4:00 
  
 **이 메시지가 표시될 위치:** Power BI 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 Microsoft 365 있습니다. 
  
 **원인:** 테넌트 ID는 guid로, xxxxxxx-xxxx-xxxx-xxxx-xxxx-xx 형식을 지정해야 합니다. 테넌트 입력란에 다른 문자열을 입력하면 이 오류가 발생합니다. 
  
 **이 오류를 해결합니다.** 관리 센터 보고서 사용 현황으로 이동하여 주 대시보드 페이지에서 Microsoft 365 사용 현황 분석 타일을 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> 찾습니다. 테넌트 ID가 타일에 나열됩니다. 여기에서 복사하여 템플릿 앱에 연결하기 위해 대화 상자에 붙여넣을 수 있습니다. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>입력하신 테넌트 ID가 시스템에서 인식되지 않습니다.

 **오류 코드:** 404 
  
 **이 메시지가 표시될 위치:** 이 Power BI 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 Microsoft 365 있습니다. 
  
 **원인:** 제공한 테넌트 ID가 유효하지 않은 경우 또는 존재하지 않습니다. 
  
 **이 오류를 해결합니다.** 관리 센터 보고서 사용 현황으로 이동하여 주 대시보드 페이지에서 Microsoft 365 사용 현황 분석 타일을 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> 찾습니다. 테넌트 ID가 타일에 나열됩니다. 여기에서 복사하여 템플릿 앱에 연결하기 위해 대화 상자에 붙여넣을 수 있습니다. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Power BI에 다시 로그인하려면 자격 증명을 다시 입력하세요.

오류 코드: 302
  
 **이 메시지가 표시될 위치:** 이 Power BI 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 Microsoft 365 있습니다. 
  
 **원인:** 인증 코드 확인에 실패하여 자격 증명을 다시 입력해야 할 수 있습니다. 
  
 **오류 수정 방법:** Power BI에서 로그아웃한 다음 다시 로그인합니다. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>이 데이터에 액세스할 수 있는 권한이 없습니다. 이 서비스에서 데이터에 대한 액세스 권한을 얻으려면 전역 관리자 또는 제품 관리자여야 합니다.

 **오류 코드:** 403 
  
 **이 메시지가 표시될 위치:** 이 Power BI 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 Microsoft 365 있습니다. 
  
 **원인:** 템플릿 앱에 연결을 시도한 사용자에게 이 데이터에 액세스하기 위한 올바른 수준의 권한 부여가 없는 경우 권한 부여 코드가 실패했습니다. 
  
 **이 오류를 해결합니다.** 전역 **관리자,** Exchange 관리자, 비즈니스용 Skype 관리자, SharePoint 관리자, 전역 읽기 프로그램 또는 보고서 읽기 프로그램인 사용자의  자격 증명을 입력하여 템플릿 앱에 연결합니다.   자세한 [내용은 관리자 역할](../add-users/about-admin-roles.md) 정보를 참조하세요. 
  
## <a name="refresh-failed"></a>새로 고치지 못했습니다.

 **이 메시지가 표시되는 위치:** Power BI 전자 메일 또는 새로 고침 기록의 실패 상태. 
  
 **원인:** 템플릿 앱에 연결된 사용자의 자격 증명이 다시 설정되고 템플릿 앱의 연결 설정에서 업데이트되지 않은 경우 사용자가 새로 고침 실패 오류를 볼 수 있습니다. 
  
 **이 오류를 해결합니다.** Power BI 사용 현황 분석 템플릿 앱에 해당하는 데이터 집합을 Microsoft 365  새로 고침 예약을 선택하고 관리자 자격 증명을 제공합니다. 
  
그래도 문제가 해결되지 않는 경우 캐시를 지우고 템플릿 앱을 다시 만듭니다.
  
  
