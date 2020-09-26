---
title: Microsoft 생산성 점수-개인 정보
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: 개인 정보를 생산성 점수가 보호 되는 방식입니다.
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287299"
---
# <a name="privacy-controls-for-productivity-score"></a><span data-ttu-id="a1b93-103">생산성 점수에 대 한 개인 정보 제어</span><span class="sxs-lookup"><span data-stu-id="a1b93-103">Privacy controls for Productivity Score</span></span>

<span data-ttu-id="a1b93-104">생산성 점수 조직은 조직이 Microsoft 365를 사용 하는 방법 및 사용자가 지 원하는 기술 환경에 대 한 정보를 활용 하 여 작업 수행 방식을 변환할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-104">Productivity Score helps organizations transform how work gets done with insights about how people use Microsoft 365 and the technology experiences that support them.</span></span> <span data-ttu-id="a1b93-105">점수는 직원 및 기술 경력에 대 한&#39;s 성과를 반영 하 고 사용자의 점수를 자신과 같은 조직과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-105">The score reflects your organization&#39;s performance against employee and technology experience measures and compares your score with organizations like yours.</span></span> <span data-ttu-id="a1b93-106">자세한 내용은 [생산성 점수 개요](productivity-score.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b93-106">For more details, check out the [Productivity Score overview](productivity-score.md) topic.</span></span>

<span data-ttu-id="a1b93-107">개인 정보 보호는 Microsoft의 개인 정보 [취급 방침을](https://privacy.microsoft.com/privacystatement)볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-107">Your privacy is important to us and you can view Microsoft's privacy statement [here](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="a1b93-108">생산성 점수에는 조직의 사용자가 작업 하는 방식에 대 한 중요 한 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-108">In Productivity Score, there is vital information that we provide on how people in your organizations work.</span></span> <span data-ttu-id="a1b93-109">따라서 정보를 의미 있는 방식으로 제대로 작동 가능 하 게 하 고 우리에 게 제공 하는 트러스트를 손상 시 키 지 않도록 제어 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-109">Thus, we also aim to provide you controls to make sure the information is actionable in a meaningful way while not compromising the trust you place in us.</span></span>

<span data-ttu-id="a1b93-110">데이터를 보다 안전 하 게 처리할 수 있도록 다음 컨트롤을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-110">We provide the following controls to allow for safer handling of data:</span></span>

- <span data-ttu-id="a1b93-111">유연한 관리자 역할-생산성 성과에서 정보를 볼 수 있는 사용자를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-111">Flexible admin roles to control who can see the information in Productivity Score.</span></span>
- <span data-ttu-id="a1b93-112">사용자 수준 메트릭에 대 한 익명화입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-112">Anonymization of user level metrics.</span></span>
- <span data-ttu-id="a1b93-113">직원 경험을 옵트아웃 하는 기능</span><span class="sxs-lookup"><span data-stu-id="a1b93-113">Capability to opt out of Employee experience.</span></span>

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a><span data-ttu-id="a1b93-114">생산성 성과에서 정보를 볼 수 있는 사용자를 제어 하기 위한 유연한 관리 역할</span><span class="sxs-lookup"><span data-stu-id="a1b93-114">Flexible admin roles to control who can see the information in Productivity Score</span></span>

<span data-ttu-id="a1b93-115">테 넌 트 수준 insights와 사용자 단위 수준 세부 정보를 비롯 하 여 관리자 역할을 사용 하 여 전체 생산성 점수 환경을 확인 하려면 역할이 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-115">To view the entire Productivity Score experience with an admin role, including tenant level insights and per-user level details, your role should be one of the following:</span></span>

- <span data-ttu-id="a1b93-116">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="a1b93-116">Global admin</span></span>
- <span data-ttu-id="a1b93-117">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="a1b93-117">Exchange admins</span></span>
- <span data-ttu-id="a1b93-118">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="a1b93-118">SharePoint admin</span></span>
- <span data-ttu-id="a1b93-119">비즈니스용 Skype 관리자</span><span class="sxs-lookup"><span data-stu-id="a1b93-119">Skype for Business admin</span></span>
- <span data-ttu-id="a1b93-120">Teams 관리자</span><span class="sxs-lookup"><span data-stu-id="a1b93-120">Teams admin</span></span>
- <span data-ttu-id="a1b93-121">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="a1b93-121">Global Reader</span></span>
- <span data-ttu-id="a1b93-122">보고서 구독자</span><span class="sxs-lookup"><span data-stu-id="a1b93-122">Reports Reader</span></span>

<span data-ttu-id="a1b93-123">변경 관리 및 채택을 담당 하는 사용자를 초대 하지만 IT 관리자는 작업을 수행할 수는 없지만, 테 넌 트 수준 insights 및 사용자별 수준 세부 정보를 비롯 하 여 전체 환경에 대 한 액세스 권한을 부여 하려면 보고서 독자 역할을 제공 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-123">To invite people who are responsible for change management and adoption but are not IT administrators into the experience, while giving them access to the complete experience including tenant level insights and per-user level details, you can give them Report Reader role.</span></span>

<span data-ttu-id="a1b93-124">직원 환경 내에서는 각 범주 세부 정보 페이지에 대 한 표 형식으로 사용자별 수준 활동 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-124">Within Employee experience, we provide per-user level activity details in grid format for each category detail page.</span></span> <span data-ttu-id="a1b93-125">이 세부 정보 수준은 생산성 점수가 모든 잠재적인 방문객에 게 적합 하지는 않으므로 Azure AD – 사용 요약 보고서 독자 역할 내에 사용자 지정 역할을 만들어 조직 내의 보다 넓은 방문자 집합에 대 한 액세스를 집계 메트릭만을 사용 하 고 환경 내의 수준별 세부 정보를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-125">As this level of detail is not suitable for all potential visitors of Productivity Score, we have created a custom role within Azure AD – Usage Summary Reports Reader role – to enable access to a wider set of visitors within your org to only the aggregate metrics and no per-level details within the experience.</span></span>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="생산성 보고서의 통신 페이지":::

## <a name="anonymization-of-user-level-metrics"></a><span data-ttu-id="a1b93-127">사용자 수준 메트릭 익명화</span><span class="sxs-lookup"><span data-stu-id="a1b93-127">Anonymization of user level metrics</span></span>

<span data-ttu-id="a1b93-128">모든 보고서에 대해 수집 되는 데이터를 익명으로 만들려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-128">To make the data that is collected for all reports anonymous, you must be a global administrator.</span></span> <span data-ttu-id="a1b93-129">이렇게 하면 생산성 점수와 Microsoft 365 사용을 포함 하 여 모든 보고서에서 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보가 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-129">This will hide identifiable information such as user, group, and site names in all reports – including Productivity Score and Microsoft 365 Usage.</span></span>

1. <span data-ttu-id="a1b93-130">관리 센터에서 조직 설정 **설정**으로 이동 하   >   **Org Settings** 고 **서비스** 탭에서 **보고서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-130">In the admin center, go to the  **Settings**  >  **Org Settings** , and under  **Services**  tab, choose  **Reports**.</span></span>
2. <span data-ttu-id="a1b93-131">**보고서** 를 선택한 다음 **생산성 점수 및 사용 현황 보고서의 사용자, 그룹 및 사이트 이름에 대 한 익명 식별자를 표시**하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-131">Select  **Reports** , and then choose to  **Display anonymous identifiers for user, group and site names in Productivity Score and Usage Reports**.</span></span> <span data-ttu-id="a1b93-132">이 설정은 사용 현황 보고서와 서식 파일 앱에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-132">This setting gets applied both to the usage reports as well as to the template app.</span></span>
3. <span data-ttu-id="a1b93-133">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-133">Select  **Save changes**.</span></span>

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="보고서에 대해 사용자 정보를 익명으로 설정 합니다.":::

## <a name="capability-to-opt-out-of-employee-experience"></a><span data-ttu-id="a1b93-135">직원 경험을 옵트아웃 하는 기능</span><span class="sxs-lookup"><span data-stu-id="a1b93-135">Capability to opt out of Employee experience</span></span>

<span data-ttu-id="a1b93-136">또한 일반적으로는 생산성 점수가 높은 직원 경험 분야를 제공할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-136">We will also provide the capability to opt out of the Employee experience area of Productivity Score at general availability.</span></span> <span data-ttu-id="a1b93-137">이 설정을 켜면 조직의 모든 사용자가 이러한 메트릭을 보고, 통신, 모임, 팀 작업, 콘텐츠 공동 작업 및 이동성 범주와 관련 된 계산에서 조직을 제거할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-137">Turning this setting on will prevent anyone from your organization being able to view these metrics and remove your organization from any calculations involving categories of Communication, Meetings, Teamwork, Content collaboration and Mobility.</span></span>

1. <span data-ttu-id="a1b93-138">관리 센터에서 조직 설정 **설정**으로 이동 하   >   **Org Settings** 고 **서비스** 탭에서 **보고서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-138">In the admin center, go to the  **Settings**  >  **Org Settings** , and under  **Services**  tab, choose  **Reports**.</span></span>
2. <span data-ttu-id="a1b93-139">**보고서** 를 선택 하 고 **org&#39;s 데이터를 생산성 성과**에 지 정보를 공유 하는 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-139">Select  **Reports** , and then un-check the box that says  **Share your org&#39;s data with Productivity Score Employee Experience insights**.</span></span> <span data-ttu-id="a1b93-140">Intune 구성 관리자에서 끝점 분석에 대 한 데이터 공유 설정을 수정 하는 방법을 이해 하려면 **자세한 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-140">To understand how to modify data-sharing settings for Endpoint Analytics in the Intune configuration manager, click on **Learn More**.</span></span>
3. <span data-ttu-id="a1b93-141">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b93-141">Select  **Save changes**.</span></span>

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="직원 경험을 제외할 수 있는 조직 설정 페이지":::