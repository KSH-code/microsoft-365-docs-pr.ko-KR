---
title: 조직 외부의 사용자와 공동 작업
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 팀에서 공동 작업을 수행 하 고 Sharepoint 사이트를 공유 하도록 외부 사용자를 초대할 때 공유 및 추가 보안을 사용 하도록 Microsoft 365을 구성 합니다.
ms.openlocfilehash: 11359e2de358d5673da6c39ca2d419c94349a829
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377416"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="e20b3-103">조직 외부의 사용자와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="e20b3-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="e20b3-104">Microsoft 365의 외부 공유 기능을 사용 하면 조직의 사용자가 파트너, 공급 업체, 고객 및 디렉터리에 계정이 없는 다른 사용자와 공동으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="e20b3-105">전체 팀 또는 사이트를 조직 외부의 사용자 또는 개별 파일에 대해서만 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="e20b3-106">조직 외부의 사용자와 공동 작업은 다음과 같은 두 가지 주요 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="e20b3-107">**공유 사용** -조직에 대해 원하는 공유 수준을 허용 하도록 Azure Active Directory, 팀, Microsoft 365 그룹 및 SharePoint에서 공유 컨트롤을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="e20b3-108">**추가 보안 사용** -조직 외부 사용자가 인증을 받도록 기본 공유 기능을 구성할 수 있지만 Microsoft 365에서는 외부에서 데이터를 보호 하 고 거 버 넌 스 정책을 유지 관리 하는 데 도움이 되는 다양 한 추가 보안 및 규정 준수 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="e20b3-109">공유 사용</span><span class="sxs-lookup"><span data-stu-id="e20b3-109">Enable sharing</span></span>

<span data-ttu-id="e20b3-110">기본적으로 Microsoft 365에서 조직 외부의 사용자와 공유는 SharePoint 및 OneDrive에 대해 사용 하도록 설정 되지만 팀에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="e20b3-111">많은 SharePoint 및 OneDrive 외부 공유 시나리오는 추가 구성 없이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="e20b3-112">사용 중인 시나리오에 대 한 설정을 확인 하거나 새로 사용 하도록 설정 하려면 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="e20b3-113">[문서 공동 작업](collaborate-on-documents.md) -파일 및 폴더에서 조직 외부의 사용자 (게스트 및 인증 되지 않은 사용자 모두)와의 공유 및 공동 작업을 허용 하도록 Microsoft 365을 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="e20b3-114">[사이트에서 공동 작업](collaborate-in-site.md) -Microsoft 365을 구성 하 여 SharePoint 사이트와 게스트 공유를 사용 하도록 설정 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="e20b3-115">[팀으로 공동 작업](collaborate-as-team.md) -팀에서 게스트 공동 작업을 사용 하도록 Microsoft 365을 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="e20b3-116">Microsoft 365에서 제공 하는 게스트 공유 설정에 대 한 자세한 내용은 [microsoft 365 guest 공유 설정 참조](microsoft-365-guest-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e20b3-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="e20b3-117">추가 보안 사용</span><span class="sxs-lookup"><span data-stu-id="e20b3-117">Enable additional security</span></span>

<span data-ttu-id="e20b3-118">조직 외부의 사용자와 공유 하는 데 사용 하려는 시나리오를 사용 하도록 설정한 경우 실수로 또는 고의적인 부적절 한 공유 로부터 콘텐츠를 보호 하는 데 도움이 되는 추가 보호책을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="e20b3-119">[인증 되지 않은 사용자와 파일 및 폴더를 공유 하는 최상의 방법](best-practices-anonymous-sharing.md) -인증 되지 않은 사용자와의 공유 모범 사례에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="e20b3-120">[실수로 인 한 노출을 제한](share-limit-accidental-exposure.md) -실수로 중요 한 콘텐츠를 조직 외부의 사용자와 공유 하는 기회를 줄이는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="e20b3-121">[보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md) -Microsoft 365에서 제공 하는 도구에 대해 설명 하 여 조직 외부의 사용자와의 공유를 안전한 방식으로 수행 하 고 거 버 넌 스 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="e20b3-122">파트너 회사와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="e20b3-122">Collaborate with partner companies</span></span>

<span data-ttu-id="e20b3-123">다른 조직의 여러 게스트가 포함 된 대규모 프로젝트에서 작업 하는 경우 또는 게스트에서 자주 변경 되는 공급 업체 관계가 있는 경우 Azure Active Directory에서 자격 관리를 사용 하 여 게스트 관리를 단순화 하 고 파트너 회사에서 해당 책임을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20b3-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="e20b3-124">자세한 내용은 [관리 되는 게스트를 사용 하 여 B2B 엑스트라넷 만들기](b2b-extranet.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e20b3-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="e20b3-125">공유 제한</span><span class="sxs-lookup"><span data-stu-id="e20b3-125">Limit sharing</span></span>

<span data-ttu-id="e20b3-126">Microsoft 365의 일부 공유 기능이 거 버 넌 스 정책과 충돌 하는 경우 공유 제한 옵션에 대 한 자세한 내용은 [microsoft 365의 공유 제한](microsoft-365-limit-sharing.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e20b3-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e20b3-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e20b3-127">Related topics</span></span>

[<span data-ttu-id="e20b3-128">Microsoft 365의 파일 공동 작업 소개</span><span class="sxs-lookup"><span data-stu-id="e20b3-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="e20b3-129">Microsoft 365을 사용 하 여 SharePoint의 파일 공동 작업 계획</span><span class="sxs-lookup"><span data-stu-id="e20b3-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
