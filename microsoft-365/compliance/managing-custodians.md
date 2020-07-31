---
title: Advanced eDiscovery에서 custodians을 사용 하 여 작업
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
description: 고급 eDiscovery의 custodian 관리 도구를 사용 하 여 법적 사례에 대 한 데이터를 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 22297edbf73f561ad46e5fae521abeb371fdc88d
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528134"
---
# <a name="work-with-custodians-and-non-custodial-data-sources-in-advanced-ediscovery"></a><span data-ttu-id="83f72-103">Advanced eDiscovery에서 custodians 및 비 custodial 데이터 원본 사용</span><span class="sxs-lookup"><span data-stu-id="83f72-103">Work with custodians and non-custodial data sources in Advanced eDiscovery</span></span>

<span data-ttu-id="83f72-104">조직이 법적 조사에 응답 하는 경우 관련 된 콘텐츠를 식별, 보존 및 수집 하는 워크플로는 관련 데이터를 custodians 조직의 구성원을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="83f72-105">EDiscovery에서는 이러한 개인을 *data custodians* (또는 *custodians*) 라고 하며 "문서 또는 전자 파일의 관리 권한을 가진 사람"으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="83f72-106">예를 들어 전자 메일 메시지의 custodian는 관련 메시지를 포함 하는 사서함의 소유자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>

<span data-ttu-id="83f72-107">또한 custodian와 연결 되지 않았지만 사례와 관련 된 콘텐츠 및 사서함에 있는 콘텐츠가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-107">Additionally, there may be content located in mailboxes and sites that aren't associated with a custodian but that's relevant to the case.</span></span> <span data-ttu-id="83f72-108">콘텐츠 위치 (사례 custodians에 관리 제어가 없지만 관련 데이터의 소유자 일 수 있음 *)을 비 custodial 데이터 원본*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-108">Content locations where case custodians don't have administrative control but may be owners of relevant data, are known as *non-custodial data sources*.</span></span>

<span data-ttu-id="83f72-109">고급 eDiscovery 사례에서는 법률 팀이 조직의 개인을 custodians으로 추가 하 고 Exchange 사서함, OneDrive 계정, SharePoint 및 팀 사이트 등의 custodial 데이터 원본을 식별 하 고 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-109">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and  identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="83f72-110">또한 custodial 되지 않는 데이터 원본을 식별 하 고 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-110">They can also identify and preserve non-custodial data sources.</span></span> <span data-ttu-id="83f72-111">고급 eDiscovery의 기본 제공 custodian 및 데이터 원본 관리 도구를 사용 하면 조직에서 실수로 또는 고의로 삭제 된 정보를 전자적으로 저장 하 여 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-111">By using the built-in custodian and data source management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="83f72-112">이를 통해 적절 한 보존 프로세스를 수동으로 수행 해야 하는 시간이 걸리고 오류가 발생 하기 쉬운 프로세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83f72-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span>

<span data-ttu-id="83f72-113">Custodians 사용에 대 한 자세한 내용은 다음 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="83f72-113">For more information about working with custodians, see the following articles:</span></span>

- [<span data-ttu-id="83f72-114">보유자를 사례에 추가</span><span class="sxs-lookup"><span data-stu-id="83f72-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="83f72-115">보유자를 사례에 일괄 추가</span><span class="sxs-lookup"><span data-stu-id="83f72-115">Bulk-add custodians to a case</span></span>](bulk-add-custodians.md)

- [<span data-ttu-id="83f72-116">사례에서 custodians 관리</span><span class="sxs-lookup"><span data-stu-id="83f72-116">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="83f72-117">보유자 활동 보기</span><span class="sxs-lookup"><span data-stu-id="83f72-117">View custodian activity</span></span>](view-custodian-activity.md)

- [<span data-ttu-id="83f72-118">비관리 데이터 원본을 사례에 추가</span><span class="sxs-lookup"><span data-stu-id="83f72-118">Add non-custodial data sources to a case</span></span>](non-custodial-data-sources.md)
