---
title: 참가자 위험 관리 알림 서식 파일
description: Microsoft 365의 참가자 위험 관리 공지 서식 파일에 대해 자세히 알아보기
keywords: Microsoft 365, 참가자 위험 관리, 위험 관리, 규정 준수
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0211eefe3c4a946bbaa4ad4c8c66e5df7b37091e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199495"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="006d2-104">참가자 위험 관리 알림 서식 파일</span><span class="sxs-lookup"><span data-stu-id="006d2-104">Insider risk management notice templates</span></span>

<span data-ttu-id="006d2-105">참가자 위험 관리 알림 서식 파일을 사용 하면 활동에서 정책 일치 및 알림을 생성 하는 경우 사용자에 게 전자 메일 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="006d2-106">대부분의 경우 경고를 생성 하는 사용자 작업은 실수로 인 한 실수 또는 실수로 인 한 의도 없이 작업의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="006d2-107">고 지 사항에 대 한 정보에 대 한 링크를 제공 하거나 회사 정책 리소스를 사용 하 여 사용자에 게 주의를 기울여야 하는 간단한 미리 알림 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="006d2-108">알림은 내부 준수 교육 프로그램의 중요 한 일부일 수 있으며, 되풀이 되는 위험 활동이 있는 사용자에 대해 문서화 된 감사 내역을 만드는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="006d2-109">문제 해결 프로세스의 일부로 서 사용자에 게 정책 일치에 대 한 전자 메일 미리 알림 알림을 보내려면 공지 템플릿 만들기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="006d2-110">검토 중인 특정 경고와 연결 된 사용자 전자 메일 주소로만 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="006d2-111">정책 일치에 적용할 알림 서식 파일을 선택 하는 경우에는 서식 파일에 정의 된 필드 값을 그대로 사용 하거나 필요에 따라 필드를 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="006d2-112">공지 템플릿 대시보드</span><span class="sxs-lookup"><span data-stu-id="006d2-112">Notice templates dashboard</span></span>

<span data-ttu-id="006d2-113">**알림 서식 파일 대시보드에** 는 구성 된 알림 서식 파일의 목록이 표시 되며, 새 알림 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="006d2-114">공지 서식 파일은 마지막에 나열 된 가장 최근 알림 서식 파일을 사용 하 여 역순 날짜 순으로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![참가자 위험 관리 알림 서식 파일 대시보드](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="006d2-116">알림 HTML</span><span class="sxs-lookup"><span data-stu-id="006d2-116">HTML for notices</span></span>

<span data-ttu-id="006d2-117">알림에 대해 단순한 텍스트 기반 전자 메일 메시지를 만들려면 공지 템플릿의 메시지 본문 필드에 HTML을 사용 하 여 보다 자세한 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="006d2-118">다음은 기본 HTML 기반 전자 메일 알림 서식 파일에 대 한 메시지 본문 형식을 제공 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="006d2-119">참가자 위험 관리 알림 서식 파일의 HTML href 특성 구현은 현재 URL 참조에 큰따옴표 대신 작은따옴표를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="006d2-120">새 공지 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="006d2-120">Create a new notice template</span></span>

<span data-ttu-id="006d2-121">새 참가자 위험 관리 알림 서식 파일을 만들려면 Microsoft 365 준수 센터의 **참가자 위험 관리** 솔루션에서 알림 마법사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="006d2-122">새 참가자 위험 관리 알림 서식 파일을 만들려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="006d2-123">[Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **참가자 위험 관리** 로 이동 하 고 **공지 서식 파일** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="006d2-124">**공지 템플릿 만들기** 를 선택 하 여 알림 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="006d2-125">**새 공지 서식 파일 만들기** 페이지에서 다음 필드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="006d2-126">**서식 파일 이름**: 알림의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="006d2-127">이 이름은 상황에 따라 알림을 보낼 때 공지 대시보드의 공지 사항 목록 및 공지 선택 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="006d2-128">**전송 원본**: 알림의 보낸 사람 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="006d2-129">이 주소는 대/소문자 로부터 알림을 보낼 때 변경 되지 않은 경우 사용자에 게 전송 되는 모든 주의 메시지의 **보낸 사람:** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="006d2-130">**참조 및 숨은 참조** 필드: 구독에 대 한 Active Directory에서 선택한 정책 일치에 대 한 알림을 받을 사용자 또는 그룹 (선택 사항)입니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="006d2-131">**제목**: 메시지의 제목 줄에 표시 되는 정보는 텍스트 문자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="006d2-132">**메시지 본문**: 메시지 본문에 표시 되는 정보는 텍스트 또는 HTML 값을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="006d2-133">공지 템플릿을 만들고 저장 하려면 **만들기** 를 선택 하 고 공지 서식 파일을 저장 하지 않고 닫으려면 **취소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="006d2-134">공지 서식 파일 업데이트</span><span class="sxs-lookup"><span data-stu-id="006d2-134">Update a notice template</span></span>

<span data-ttu-id="006d2-135">기존 참가자 위험 관리 알림 서식 파일을 업데이트 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="006d2-136">[Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **참가자 위험 관리** 로 이동 하 고 **공지 서식 파일** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="006d2-137">공지 사항 대시보드에서 관리 하려는 공지 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="006d2-138">알림 세부 정보 페이지에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="006d2-139">**편집** 페이지에서는 다음 필드를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="006d2-140">**서식 파일 이름**: 알림의 새 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="006d2-141">이 이름은 상황에 따라 알림을 보낼 때 공지 대시보드의 공지 사항 목록 및 공지 선택 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="006d2-142">**전송 원본**: 알림의 보낸 사람 전자 메일 주소를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="006d2-143">이 주소는 대/소문자 로부터 알림을 보낼 때 변경 되지 않은 경우 사용자에 게 전송 되는 모든 주의 메시지의 **보낸 사람:** 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="006d2-144">**참조 및 숨은 참조** 필드: 구독에 대 한 Active Directory에서 선택한 정책 일치에 대 한 알림을 받을 수 있는 선택적 사용자 또는 그룹을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="006d2-145">**제목**: 메시지의 제목 줄에 표시 되는 업데이트 정보는 텍스트 문자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="006d2-146">**메시지 본문**: 메시지 본문에 표시 되는 업데이트 정보는 텍스트 또는 HTML 값을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="006d2-147">알림을 업데이트 및 저장 하려면 **저장** 을 선택 하 고 공지 서식 파일을 저장 하지 않고 닫으려면 **취소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="006d2-148">공지 서식 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="006d2-148">Delete a notice template</span></span>

<span data-ttu-id="006d2-149">기존 참가자 위험 관리 알림 서식 파일을 삭제 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="006d2-150">[Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **참가자 위험 관리** 로 이동 하 고 **공지 서식 파일** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="006d2-151">알림 대시보드에서 삭제할 알림 서식 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="006d2-152">도구 모음에서 **삭제** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="006d2-153">공지 서식 파일을 삭제 하려면 삭제 대화 상자에서 **예** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="006d2-154">삭제를 취소 하려면 **취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="006d2-154">To cancel the deletion, select **Cancel**.</span></span>
