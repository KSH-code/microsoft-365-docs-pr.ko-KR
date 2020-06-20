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
ms.openlocfilehash: 400793a6779cef5b1e823f40fa08cc1e05f93f15
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815495"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a><span data-ttu-id="e82af-103">Advanced eDiscovery에서 custodians을 사용 하 여 작업</span><span class="sxs-lookup"><span data-stu-id="e82af-103">Work with custodians in Advanced eDiscovery</span></span>

<span data-ttu-id="e82af-104">조직이 법적 조사에 응답 하는 경우 관련 된 콘텐츠를 식별, 보존 및 수집 하는 워크플로는 관련 데이터를 custodians 조직의 구성원을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="e82af-105">EDiscovery에서는 이러한 개인을 *data custodians* (또는 *custodians*) 라고 하며 "문서 또는 전자 파일의 관리 권한을 가진 사람"으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="e82af-106">예를 들어 전자 메일 메시지의 custodian는 관련 메시지를 포함 하는 사서함의 소유자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>  

<span data-ttu-id="e82af-107">조사가 시작 되 면 eDiscovery 팀은 사례와 관련 된 모든 관련 custodians 및 데이터 원본을 빠르게 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-107">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="e82af-108">시간이 지남에 따라 custodians 목록과 해당 데이터 원본이 증가 하거나 감소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-108">Over time, the list of custodians and their data sources may increase or decrease.</span></span> <span data-ttu-id="e82af-109">따라서 조직은 사례 수명 주기 동안 custodial 콘텐츠를 식별, 보존 및 수집 하는 제어 된 프로세스를 유지 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-109">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="e82af-110">고급 eDiscovery 사례에서는 법률 팀이 조직의 개인을 custodians으로 추가 하 고 Exchange 사서함, OneDrive 계정, SharePoint 및 팀 사이트 등의 custodial 데이터 원본을 자동으로 식별 하 고 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-110">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="e82af-111">고급 eDiscovery의 기본 제공 custodian 관리 도구를 사용 하면 조직에서 실수로 또는 고의로 삭제 된 정보를 전자적으로 저장 하 여 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-111">By using the built-in custodian management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="e82af-112">이를 통해 적절 한 보존 프로세스를 수동으로 수행 해야 하는 시간이 걸리고 오류가 발생 하기 쉬운 프로세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82af-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span> 

<span data-ttu-id="e82af-113">Custodians 사용에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e82af-113">For more information about working with custodians, see the following:</span></span> 

- [<span data-ttu-id="e82af-114">보유자를 사례에 추가</span><span class="sxs-lookup"><span data-stu-id="e82af-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="e82af-115">사례에서 custodians 관리</span><span class="sxs-lookup"><span data-stu-id="e82af-115">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="e82af-116">보유자 활동 보기</span><span class="sxs-lookup"><span data-stu-id="e82af-116">View custodian activity</span></span>](view-custodian-activity.md)
