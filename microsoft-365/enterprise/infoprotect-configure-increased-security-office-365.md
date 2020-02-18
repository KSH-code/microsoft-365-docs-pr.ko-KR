---
title: '3단계: Office 365에 대한 향상된 보안 구성'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365에 대한 향상된 보안을 이해하고 구성하십시오.
ms.openlocfilehash: eabf0d60f3cfb61b7fffcc688a080ba99f83293e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067245"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="260be-103">3단계: Office 365에 대한 향상된 보안 구성</span><span class="sxs-lookup"><span data-stu-id="260be-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="260be-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="260be-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="260be-106">Microsoft 365 구독 및 해당 데이터가 시작되어 악의적인 위협으로부터 안전하게 보호되도록 다음을 구성하십시오.</span><span class="sxs-lookup"><span data-stu-id="260be-106">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="260be-107">위협 관리 정책 조정</span><span class="sxs-lookup"><span data-stu-id="260be-107">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="260be-108">추가 Exchange 온라인 테넌트 전체 설정</span><span class="sxs-lookup"><span data-stu-id="260be-108">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="260be-109">SharePoint 관리 센터의 테넌트 전체 공유 정책</span><span class="sxs-lookup"><span data-stu-id="260be-109">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="260be-110">Azure Active Directory(Azure AD)의 설정</span><span class="sxs-lookup"><span data-stu-id="260be-110">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="260be-111">구성한 후에는 다음에서 보안 상태에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="260be-111">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="260be-112">Microsoft 보안 센터의 대시보드 및 보고서</span><span class="sxs-lookup"><span data-stu-id="260be-112">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="260be-113">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="260be-113">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="260be-114">추가 보안 기능은 [Office 365 ATP(Advanced Threat Protection)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)로, 다음을 통해 조직이 보다 안전하게 협업할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="260be-114">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="260be-115">전자 메일의 [링크](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) 및 [첨부파일](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) 보호</span><span class="sxs-lookup"><span data-stu-id="260be-115">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="260be-116">Exchange 온라인 및 [SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 파일](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)에 정보 도용 및 피싱 방지 기능 제공</span><span class="sxs-lookup"><span data-stu-id="260be-116">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="260be-117">Office 365 ATP는 Microsoft 365 E5에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="260be-117">Office 365 ATP is only available with Microsoft 365 E5.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="260be-119">테스트 랩 가이드: 강화된 Microsoft 365 보안 구성</span><span class="sxs-lookup"><span data-stu-id="260be-119">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="260be-120">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step3)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="260be-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="260be-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="260be-121">Next step</span></span>


|||
|:-------|:-----|
|![4단계](../media/stepnumbers/Step4.png)|[<span data-ttu-id="260be-123">WIP(Windows Information Protection) 구성</span><span class="sxs-lookup"><span data-stu-id="260be-123">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


