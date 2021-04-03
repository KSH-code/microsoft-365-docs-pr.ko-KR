---
title: 게스트 계정에 대한 필수 구성 요소
description: 게스트 계정에 대한 구성 지침 및 조정 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574610"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="920e2-104">게스트 계정에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="920e2-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="920e2-105">Microsoft Managed Desktop을 사용하려면 Azure AD 조직에서 게스트 계정 액세스를 위해 다음 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="920e2-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="920e2-106">외부 ID/외부 공동 작업에서 [Azure Portal에서](https://portal.azure.com) **이러한 설정을 조정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="920e2-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="920e2-107">**게스트 초대자** 역할의 관리자 및 사용자는 예로 설정하여 초대할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="920e2-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="920e2-108">공동 **작업 제한의 경우** 다음 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="920e2-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="920e2-109">초대를 모든 도메인(가장 포함)으로 보내기 허용을 선택하면 다른 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="920e2-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="920e2-110">지정된 도메인에 대한 초대 거부를 선택하는 경우 대상 도메인에 Microsoft.com 목록에 없는지 확인 합니다. </span><span class="sxs-lookup"><span data-stu-id="920e2-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="920e2-111">지정된 **도메인(가장** 제한적인)에 대한 초대만 허용을 선택하는 경우  대상 도메인에 Microsoft.com 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="920e2-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="920e2-112">이러한 설정과 상호 작용하는 제한을 설정하는 경우 Azure Active Directory 최신 작업 공간 서비스 계정 을 **제외해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="920e2-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="920e2-113">예를 들어 게스트 계정이 Intune 포털에 액세스하지 못하게 하는 조건부 액세스 정책이 있는 경우 이 정책에서 최신 **작업** 공간 서비스 계정 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="920e2-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="920e2-114">준비 단계</span><span class="sxs-lookup"><span data-stu-id="920e2-114">Steps to get ready</span></span>

1. <span data-ttu-id="920e2-115">[Microsoft Managed Desktop의 선행 준비를 검토합니다.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="920e2-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="920e2-116">준비 [평가 도구 사용.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="920e2-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="920e2-117">[게스트 계정의 선행 준비(이](guest-accounts.md) 문서)</span><span class="sxs-lookup"><span data-stu-id="920e2-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="920e2-118">Microsoft Managed Desktop의 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="920e2-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="920e2-119">Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비</span><span class="sxs-lookup"><span data-stu-id="920e2-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="920e2-120">Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비</span><span class="sxs-lookup"><span data-stu-id="920e2-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="920e2-121">Microsoft Managed Desktop의 앱</span><span class="sxs-lookup"><span data-stu-id="920e2-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="920e2-122">Microsoft Managed Desktop의 매핑된 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="920e2-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="920e2-123">Microsoft Managed Desktop의 인쇄 리소스 준비</span><span class="sxs-lookup"><span data-stu-id="920e2-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)