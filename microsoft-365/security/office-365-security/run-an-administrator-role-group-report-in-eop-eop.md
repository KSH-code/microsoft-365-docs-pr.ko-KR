---
title: EOP에서 관리자 역할 그룹 보고서 실행
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 EOP (Exchange Online Protection)에서 관리자 역할 그룹 보고서를 실행 하는 방법을 알아봅니다.
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034459"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="223ed-103">EOP에서 관리자 역할 그룹 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="223ed-103">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="223ed-104">관리자가 구성원을 관리 역할 그룹에 추가 하거나 멤버를 제거 하면 EOP (Exchange Online Protection)에서 각 항목을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-104">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="223ed-105">EAC (Exchange 관리 센터)에서 관리자 역할 그룹 보고서를 실행 하면 항목이 검색 결과로 표시 되 고 영향을 받는 역할 그룹, 역할 그룹 구성원 자격을 변경한 사용자 및 멤버 자격 업데이트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-105">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="223ed-106">이 보고서를 사용하여 조직의 사용자에게 할당된 관리 권한의 변경을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-106">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="223ed-107">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="223ed-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="223ed-108">예상 완료 시간: 2분</span><span class="sxs-lookup"><span data-stu-id="223ed-108">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="223ed-109">Exchange 관리 센터를 열려면 exchange [Online Protection의 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="223ed-109">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="223ed-p102">이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 확인하려면 다음을 참조하세요. [EOP의 기능 사용 권한](feature-permissions-in-eop.md)의 "보고서" 섹션</span><span class="sxs-lookup"><span data-stu-id="223ed-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="223ed-112">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="223ed-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="223ed-113">문제가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="223ed-113">Having problems?</span></span> <span data-ttu-id="223ed-114">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="223ed-114">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="223ed-115">EAC를 사용하여 관리자 역할 그룹 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="223ed-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="223ed-116">관리자 역할 그룹 보고서를 실행 하 여 특정 시간대 내에 조직의 관리 역할 그룹에 대 한 변경 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="223ed-117">EAC에서 **준수 관리** \> **감사**로 이동한 후 **관리자 역할 그룹 보고서 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="223ed-p104">**시작 날짜**와 **끝 날짜**를 선택합니다. 기본적으로 보고서는 지난 2주 동안의 관리자 역할 그룹 변경 내용을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-p104">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="223ed-p105">특정 역할 그룹에 대한 변경 내용을 보려면 **역할 그룹 선택**을 클릭합니다. 그러면 표시되는 대화 상자에서 역할 그룹을 하나 이상 선택하고 **확인**을 클릭합니다. 변경된 모든 역할 그룹을 찾으려는 경우에는 해당 필드를 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-p105">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="223ed-123">**검색**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-123">Click **Search**.</span></span>

<span data-ttu-id="223ed-p106">지정한 조건을 사용하여 찾은 변경 내용은 결과 창에 표시됩니다. 검색 결과에서 역할 그룹을 클릭하여 세부 정보 창에서 변경 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-p106">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="223ed-126">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="223ed-126">How do you know this worked?</span></span>

<span data-ttu-id="223ed-p107">관리자 역할 그룹 보고서를 성공적으로 실행한 경우 날짜 범위 내에서 변경된 역할 그룹은 검색 결과 창에 표시됩니다. 결과가 표시되지 않으면 지정된 날짜 범위 내에서 역할 그룹이 변경되지 않은 것입니다. 표시할 결과가 있다고 생각되면 날짜 범위를 변경한 다음 보고서를 다시 실행하십시오.</span><span class="sxs-lookup"><span data-stu-id="223ed-p107">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="223ed-130">역할 그룹 구성원의 변경 모니터링</span><span class="sxs-lookup"><span data-stu-id="223ed-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="223ed-p108">구성원이 역할 그룹에서 추가되거나 제거되면 세부 정보 창에 표시되는 검색 결과에서 역할 그룹 구성원이 업데이트되었음이 표시되고 현재 구성원이 표시됩니다. 이 결과에서는 추가되거나 제거된 사용자가 명시적으로 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-p108">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="223ed-p109">사용자가 추가되었거나 제거되었는지 확인하려면 보고서에서 두 가지 항목을 비교해야 합니다. 예를 들어 **HelpDesk** 역할 그룹에 대한 다음 로그 항목을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-p109">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="223ed-135">오후 1/27/2018 4:43</span><span class="sxs-lookup"><span data-stu-id="223ed-135">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="223ed-136">관리자</span><span class="sxs-lookup"><span data-stu-id="223ed-136">Administrator</span></span> <br> <span data-ttu-id="223ed-137">업데이트된 구성원: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="223ed-137">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="223ed-138">오전 2/06/2018 10:09</span><span class="sxs-lookup"><span data-stu-id="223ed-138">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="223ed-139">관리자</span><span class="sxs-lookup"><span data-stu-id="223ed-139">Administrator</span></span> <br> <span data-ttu-id="223ed-140">업데이트된 구성원: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="223ed-140">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="223ed-141">오후 2/19/2018 2:12</span><span class="sxs-lookup"><span data-stu-id="223ed-141">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="223ed-142">관리자</span><span class="sxs-lookup"><span data-stu-id="223ed-142">Administrator</span></span> <br> <span data-ttu-id="223ed-143">업데이트된 구성원: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="223ed-143">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="223ed-144">이 예에서 관리자 사용자 계정은 다음과 같이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-144">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="223ed-145">2/06/2018에는 사용자 tonip가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-145">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="223ed-146">2/19/2018에서는 사용자가 pilarp를 제거 했습니다.</span><span class="sxs-lookup"><span data-stu-id="223ed-146">On 2/19/2018, they removed the user pilarp.</span></span>
