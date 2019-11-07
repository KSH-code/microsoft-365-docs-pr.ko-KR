---
title: 조건부 액세스 조정
description: 특정 Microsoft 계정을 제외 하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1b91186837ad558965d675f82d013a7081c7c7ec
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012493"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="09ba1-104">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="09ba1-104">Adjust conditional access</span></span>

<span data-ttu-id="09ba1-105">조직에서 [조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 정책을 사용 하는 경우에는 Microsoft Managed Desktop이 제대로 작동할 수 있도록 사용자가 특정 계정을 제외 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ba1-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="09ba1-106">이렇게 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="09ba1-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="09ba1-107">[방법: Azure Active Directory에서 조건부 액세스 배포 계획](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps)의 "롤백 단계" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09ba1-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="09ba1-108">이 단계에 따라 모든 정책에 대 한 *최신 직장의 작업 공간 서비스 계정* 그룹을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ba1-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="09ba1-109">조건부 액세스에 어려움이 있으면 관리자 [지원](../working-with-managed-desktop/admin-support.md)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="09ba1-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="09ba1-110">Microsoft Managed Desktop을 시작 하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="09ba1-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="09ba1-111">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="09ba1-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="09ba1-112">조건부 액세스 조정 (이 항목)</span><span class="sxs-lookup"><span data-stu-id="09ba1-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="09ba1-113">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="09ba1-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="09ba1-114">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="09ba1-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="09ba1-115">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="09ba1-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="09ba1-116">장치 설정</span><span class="sxs-lookup"><span data-stu-id="09ba1-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="09ba1-117">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="09ba1-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="09ba1-118">앱 배포</span><span class="sxs-lookup"><span data-stu-id="09ba1-118">Deploy apps</span></span>](deploy-apps.md)