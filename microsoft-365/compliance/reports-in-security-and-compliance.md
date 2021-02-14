---
title: 보안 및 준수 센터의 보고서
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 보안 및 & 준수 센터를 사용하여 SharePoint Online 및 Exchange Online 조직에 대한 다양한 보고서와 Azure Active Directory 보고서를 볼 수 있습니다.
ms.openlocfilehash: 8762c1bbb23d2b9f3840076f0ffa465cf7ab264b
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936181"
---
# <a name="reports-in-the-security--compliance-center"></a>보안 및 준수 센터의 보고서

보안 및 준수 센터의 보고서 보기 **페이지를** & SharePoint Online 및 Exchange Online 조직의 감사 보고서에 빠르게 액세스할 수 있습니다. 보고서 보기 페이지에서 Azure AD(Active Directory) 사용자 로그인 보고서, 사용자 활동 보고서 및 Azure AD 감사 로그에 액세스할 **수도** 있습니다. 이는 유료 Microsoft 365 구독에 Microsoft Azure에 대한 무료 구독이 포함되어 있기 때문에입니다. 이러한 Azure 보고서에 처음 액세스하려고 하면 일회성 등록 프로세스를 완료해야 합니다. 
  
> [!TIP]
> 조직의 활동에 대한 추가 보고서를 확인하려면 [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)관리 센터의 활동 보고서를 참조하세요. 
  
 **시작하기 전에**
  
보안 및 준수 센터에서 보고서를 볼 & 권한이 필요합니다.
  
- 보안 및 준수 센터에서 보고서를 보기 위해 EAC(Exchange 관리 센터)에서 보안 읽기 & 할당해야 합니다. 기본적으로 이 역할은 EAC의 조직 관리 및 보안 독자 역할 그룹에 할당됩니다.
    
- 보안 및 준수 센터에서 DLP 보고서를 View-Only DLP 보고서를 & DLP 규정 준수 센터에서 & 할당해야 합니다. 기본적으로 이 역할은 Security & 준수 센터의 준수 관리자, 조직 관리, 보안 관리자 및 보안 읽기 권한자 역할 그룹에 할당됩니다.

- 또한 EAC에서 DLP 보고서를 View-Only 받는 사람 역할을 EAC에서 할당해야 합니다. 기본적으로 이 역할은 EAC의 준수 관리, View-Only 관리 및 조직 관리 역할 그룹에 할당됩니다.
  
 **보안 및 준수 센터에서 보고서 보기 페이지를 &:**
  
1. [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)으로 이동합니다.
    
2. 조직의 사용자 계정에 대한 자격 증명을 사용하여 로그인합니다.
    
보고서 **보기 페이지에서** 다음 유형의 보고서를 볼 수 있습니다. 
  
- [감사 보고서](#auditing-reports)
- [관리 검토 보고서](#supervisory-review-report)
- [데이터 손실 방지 역할](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>감사 보고서

다음 표에서는 보안 및  준수 센터의  보고서 보기 페이지에 있는 & 설명합니다. 
  
|**보고서**|**설명**|
|:-----|:-----|
|**감사 로그 보고서** <br/> |감사 로그에서 조직의 사용자 및 관리자 활동을 검색할 수 있습니다. 보고서에는 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Office 365의 디렉터리 서비스인 Azure Active Directory의 항목 사용자 및 관리자 활동이 포함됩니다. 자세한 내용은 [Office 365에서](search-the-audit-log-in-security-and-compliance.md)감사 로그 검색을 참조하세요.  <br/> |
|**Azure 광고 보고서** <br/> |조직에서 비정상적 또는 의심스러운 로그인 활동을 찾아보기 위해 Microsoft Azure에서 로그인 및 활동 보고서를 사용할 수 있습니다. Azure AD 감사 로그에서 이벤트를 볼 수도 있습니다. Azure에서 보고서를 보려면 Azure AD 보고서 **보기를 클릭합니다.** 자세한 내용은 다음을 참조하세요. <br/><br/>[Office 365에서 무료 Azure Active Directory 구독을 사용하세요.](use-your-free-azure-ad-subscription-in-office-365.md) <br/> [액세스 및 사용 현황 보고서 보기.](https://go.microsoft.com/fwlink/p/?LinkId=506902)  <br/> |
|
            Exchange 감사 보고서 <br/> | Microsoft 365의 감사 기능을 사용하여 조직의 관리자가 Exchange Online 구성에 적용한 변경 내용을 추적할 수 있습니다. Microsoft 데이터 센터 관리자 또는 위임된 관리자가 Exchange Online 조직에 적용한 변경 내용도 기록됩니다. Exchange Online의 경우 관리자 감사 로깅은 기본적으로 사용하도록 설정되어 있으므로 켜기 위해 아무 것도 할 일이 없습니다. 또한 Exchange Online에서는 사서함 소유자가 아니라 다른 사용자가 사서함에 대한 액세스를 추적할 수 있도록 사서함 감사 로깅을 제공합니다. 비소유자의 액세스를 추적하려는 각 사서함에 대해 사서함 감사 로깅을 사용하도록 설정해야 합니다.  <br/>  관리자와 사서함 감사 로깅, 감사 로그 항목을 볼 수 있는 감사 보고서를 실행할 수 있습니다. 받은 24 시간 이내에 게 전자 메일 메시지에 첨부 된 XML 파일에 있는 사서함 및 관리자 감사 로그를 내보낼 수 있습니다. <br/><br/>감사 로그에 대한 자세한 내용은 를 참조하십시오.  <br/><br/> [사서함 감사 로그 내보내기](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [데이터 센터 관리자 감사 로그 보기 및 내보내기](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [역할 그룹 변경 또는 관리자 감사 로그 검색](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 감사 보고서.](https://go.microsoft.com/fwlink/p/?LinkID=395232)  <br/> |
   
## <a name="supervisory-review-report"></a>관리 검토 보고서

관리 검토 보고서를 사용하면 조직의 모든 관리 검토 정책 상태를 볼 수 있습니다. 자세한 내용은 조직에 대한 관리 검토 정책 [구성을 참조하세요.](configure-supervision-policies.md)
  
## <a name="data-loss-prevention-reports"></a>데이터 손실 방지 역할

DLP(데이터 손실 방지) 보고서에는 DLP 정책에 대한 정보와 콘텐츠에 적용된 규칙에 대한 정보가 들어 있습니다. DLP 정책 및 규칙에 기초 했던 DLP 동작에 대 한 정보를 표시 하도록 보고서를 구성할 수 있습니다. 자세한 내용은 데이터 손실 [방지에 대한 보고서 보기를 참조하세요.](view-the-dlp-reports.md)
