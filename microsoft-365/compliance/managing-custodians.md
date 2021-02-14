---
title: Advanced eDiscovery에서 보전자들과 작업
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Advanced eDiscovery의 상주 관리 도구를 사용하여 법률 사례에 대한 데이터를 관리하는 방법을 자세히 알아보는 방법을 배울 수 있습니다.
ms.openlocfilehash: 22297edbf73f561ad46e5fae521abeb371fdc88d
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528134"
---
# <a name="work-with-custodians-and-non-custodial-data-sources-in-advanced-ediscovery"></a><span data-ttu-id="ff814-103">Advanced eDiscovery에서 보호자 및 비보조 데이터 원본 사용</span><span class="sxs-lookup"><span data-stu-id="ff814-103">Work with custodians and non-custodial data sources in Advanced eDiscovery</span></span>

<span data-ttu-id="ff814-104">조직이 법적 조사에 응답하면 관련성 있는 콘텐츠를 식별, 보존 및 수집하는 워크플로는 관련 데이터의 양도인 조직의 사용자에 따라 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="ff814-105">eDiscovery에서 이러한 개인을  데이터 관리자(또는 관리자만)라고 부르며 "문서 또는 전자 파일의 관리 제어를 갖는 사람"으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="ff814-106">예를 들어 전자 메일 메시지의 소유자는 관련 메시지가 포함된 사서함의 소유자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>

<span data-ttu-id="ff814-107">또한 사서함 및 사이트에는 양도자와 연결되지 않지만 해당 사례와 관련이 있는 콘텐츠가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-107">Additionally, there may be content located in mailboxes and sites that aren't associated with a custodian but that's relevant to the case.</span></span> <span data-ttu-id="ff814-108">사례 소유자는 관리 제어가 없지만 관련 데이터의 소유자일 수 있는 콘텐츠 위치를 비관리 데이터 원본으로 알려져 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="ff814-108">Content locations where case custodians don't have administrative control but may be owners of relevant data, are known as *non-custodial data sources*.</span></span>

<span data-ttu-id="ff814-109">Advanced eDiscovery 사례에서 법률 팀은 조직의 개인을 관리인으로 추가하고, Exchange 사서함, OneDrive 계정, SharePoint 및 Teams 사이트와 같은 관리 데이터 원본을 식별하고 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-109">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and  identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="ff814-110">또한 비보조 데이터 원본을 식별하고 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-110">They can also identify and preserve non-custodial data sources.</span></span> <span data-ttu-id="ff814-111">Advanced eDiscovery에서 기본 제공 보관 및 데이터 원본 관리 도구를 사용하여 조직은 의도하지 않은(또는 의도적인) 지우기로부터 전자적으로 저장된 정보를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-111">By using the built-in custodian and data source management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="ff814-112">이렇게 하면 법적 보유 프로세스를 수동으로 수행할 때 시간이 많이 걸리고 오류가 발생하기 쉽게 하는 프로세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff814-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span>

<span data-ttu-id="ff814-113">보호자에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff814-113">For more information about working with custodians, see the following articles:</span></span>

- [<span data-ttu-id="ff814-114">보유자를 사례에 추가</span><span class="sxs-lookup"><span data-stu-id="ff814-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="ff814-115">보유자를 사례에 일괄 추가</span><span class="sxs-lookup"><span data-stu-id="ff814-115">Bulk-add custodians to a case</span></span>](bulk-add-custodians.md)

- [<span data-ttu-id="ff814-116">사례의 관리</span><span class="sxs-lookup"><span data-stu-id="ff814-116">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="ff814-117">보유자 활동 보기</span><span class="sxs-lookup"><span data-stu-id="ff814-117">View custodian activity</span></span>](view-custodian-activity.md)

- [<span data-ttu-id="ff814-118">비관리 데이터 원본을 사례에 추가</span><span class="sxs-lookup"><span data-stu-id="ff814-118">Add non-custodial data sources to a case</span></span>](non-custodial-data-sources.md)
