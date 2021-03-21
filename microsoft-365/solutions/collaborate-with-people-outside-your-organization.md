---
title: 조직 외부 사용자와 공동 작업
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: 조직 외부의 사용자와 공동 작업을 위해 Teams, OneDrive 및 SharePoint와 같은 Microsoft 365 앱을 구성하는 방법을 학습합니다.
ms.openlocfilehash: 359e72c12c43ca1ea984f93d87ab4868e6d1eb66
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916397"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="fed58-103">조직 외부 사용자와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="fed58-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="fed58-104">Microsoft 365의 외부 공유 기능을 통해 조직의 사용자가 디렉터리에 계정이 없는 파트너, 공급업체, 고객 및 다른 사용자와 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="fed58-105">전체 팀 또는 사이트를 조직 외부의 사용자나 개별 파일과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="fed58-106">조직 외부의 사용자와 공동 작업하는 작업은 다음 두 가지 주요 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="fed58-107">**공유 사용** - 조직에 원하는 공유 수준을 허용하도록 Azure Active Directory, Teams, Microsoft 365 그룹 및 SharePoint에서 공유 컨트롤을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="fed58-108">**추가 보안** 사용 - 조직 외부의 사용자가 인증을 하도록 기본 공유 기능을 구성할 수 있는 반면, Microsoft 365는 외부에서 공유하는 동안 데이터를 보호하고 거버넌스 정책을 유지 관리하는 데 도움이 되는 다양한 추가 보안 및 규정 준수 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="fed58-109">공유 사용</span><span class="sxs-lookup"><span data-stu-id="fed58-109">Enable sharing</span></span>

<span data-ttu-id="fed58-110">기본적으로 Microsoft 365에서는 조직 외부의 사용자와 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-110">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="fed58-111">많은 외부 공유 시나리오는 추가 구성 없이 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-111">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="fed58-112">사용 중인 시나리오의 설정을 확인하거나 새 설정을 사용하도록 설정하려면 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="fed58-113">[문서](collaborate-on-documents.md) 공동 작업 - 파일 및 폴더에서 조직 외부의 사용자(게스트 및 비인식 사용자 모두)와의 공유 및 공동 작업을 허용하도록 Microsoft 365를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="fed58-114">[사이트에서 공동 작업](collaborate-in-site.md) - 게스트와 SharePoint 사이트를 공유하도록 Microsoft 365를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="fed58-115">[팀으로 공동 작업](collaborate-as-team.md) - Teams에서 게스트 공동 작업을 사용하도록 Microsoft 365를 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="fed58-116">Microsoft 365에서 사용할 수 있는 게스트 공유 설정에 대한 포괄적인 내용은 [Microsoft 365 게스트](microsoft-365-guest-settings.md)공유 설정 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fed58-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="fed58-117">추가 보안 사용</span><span class="sxs-lookup"><span data-stu-id="fed58-117">Enable additional security</span></span>

<span data-ttu-id="fed58-118">조직 외부의 사용자와 공유하는 데 사용할 시나리오를 사용하도록 설정한 후 추가 보호책을 고려하여 실수로 또는 의도적으로 부적절한 공유로부터 콘텐츠를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="fed58-119">[Best practices for sharing files and folders with unauthenticated users(파일](best-practices-anonymous-sharing.md) 및 폴더를 공유하기 위한 모범 사례) - 비인식 사용자와 공유하기 위한 모범 사례에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="fed58-120">[우발적 노출](share-limit-accidental-exposure.md) 제한 - 조직 외부의 사용자와 실수로 중요한 콘텐츠를 공유하는 위험을 줄이는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="fed58-121">[안전한](create-secure-guest-sharing-environment.md) 게스트 공유 환경 만들기 - 조직 외부의 사용자와의 공유가 안전하고 안전한 방식으로 수행되도록 지원하기 위해 Microsoft 365에서 제공하는 도구에 대해 알아보고 거버넌스 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="fed58-122">파트너 회사와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="fed58-122">Collaborate with partner companies</span></span>

<span data-ttu-id="fed58-123">다른 조직의 많은 게스트가 참여하는 대규모 프로젝트에서 작업하거나 게스트가 자주 변경되는 지속적인 공급업체 관계가 있는 경우 Azure Active Directory에서 권한 관리를 사용하여 게스트 관리를 간소화하고 파트너 회사가 해당 책임에서 공유할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="fed58-124">자세한 [내용은 관리되는 게스트를 사용하여 B2B 엑스트라넷](b2b-extranet.md) 만들기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fed58-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="fed58-125">공유 제한</span><span class="sxs-lookup"><span data-stu-id="fed58-125">Limit sharing</span></span>

<span data-ttu-id="fed58-126">Microsoft 365의 공유 기능 중 일부가 거버넌스 정책과 충돌하는 경우 [Microsoft 365에서](microsoft-365-limit-sharing.md) 공유 제한을 참조하여 공유 제한 옵션에 대해 자세히 알아보하세요.</span><span class="sxs-lookup"><span data-stu-id="fed58-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fed58-127">관련 주제</span><span class="sxs-lookup"><span data-stu-id="fed58-127">Related topics</span></span>

[<span data-ttu-id="fed58-128">Microsoft 365의 파일 공동 작업 진행</span><span class="sxs-lookup"><span data-stu-id="fed58-128">Intro to file collaboration in Microsoft 365</span></span>](/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="fed58-129">Microsoft 365를 통해 SharePoint에서 파일 공동 작업 계획</span><span class="sxs-lookup"><span data-stu-id="fed58-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](/sharepoint/deploy-file-collaboration)