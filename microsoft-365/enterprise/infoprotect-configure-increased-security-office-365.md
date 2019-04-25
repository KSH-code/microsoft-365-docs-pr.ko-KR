---
title: '3단계: Office 365에 대한 향상된 보안 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365에 대한 향상된 보안을 이해하고 구성하십시오.
ms.openlocfilehash: a1976a9305c40d721bd56a4b21b8a52552c1a9dc
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285084"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="1ad4d-103">3단계: Office 365에 대한 향상된 보안 구성</span><span class="sxs-lookup"><span data-stu-id="1ad4d-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="1ad4d-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="1ad4d-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="1ad4d-105">Microsoft 365 구독 및 해당 데이터가 시작되어 악의적인 위협으로부터 안전하게 보호되도록 다음을 구성하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ad4d-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see Configure your Office 365 tenant for increased security and configure the following additional security:</span></span>

- [<span data-ttu-id="1ad4d-106">위협 관리 정책 조정</span><span class="sxs-lookup"><span data-stu-id="1ad4d-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="1ad4d-107">추가 Exchange 온라인 테넌트 전체 설정</span><span class="sxs-lookup"><span data-stu-id="1ad4d-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="1ad4d-108">SharePoint 관리 센터의 테넌트 전체 공유 정책</span><span class="sxs-lookup"><span data-stu-id="1ad4d-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="1ad4d-109">Azure Active Directory(Azure AD)의 설정</span><span class="sxs-lookup"><span data-stu-id="1ad4d-109">Settings in Azure Active Directory</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="1ad4d-110">구성한 후에는 다음에서 보안 상태에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad4d-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="1ad4d-111">Microsoft 보안 센터의 대시보드 및 보고서</span><span class="sxs-lookup"><span data-stu-id="1ad4d-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="1ad4d-112">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="1ad4d-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="1ad4d-113">추가 보안 기능은 [Office 365 ATP(Advanced Threat Protection)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)로, 다음을 통해 조직이 보다 안전하게 협업할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ad4d-113">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="1ad4d-114">전자 메일의 [링크](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) 및 [첨부파일](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) 보호</span><span class="sxs-lookup"><span data-stu-id="1ad4d-114">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="1ad4d-115">Exchange 온라인 및 [SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 파일](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)에 정보 도용 및 피싱 방지 기능 제공</span><span class="sxs-lookup"><span data-stu-id="1ad4d-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

<span data-ttu-id="1ad4d-116">Office 365 ATP 에서만 Microsoft 365 Enterprise E5와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad4d-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="1ad4d-118">테스트 랩 가이드: 강화된 Microsoft 365 보안 구성</span><span class="sxs-lookup"><span data-stu-id="1ad4d-118">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="1ad4d-119">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step4)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1ad4d-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="1ad4d-120">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1ad4d-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="1ad4d-121">권한이 부여된 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="1ad4d-121">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


