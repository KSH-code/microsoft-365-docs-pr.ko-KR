---
title: 내부자 위험 관리 알림 템플릿
description: 내부자 위험 관리 알림 템플릿에 대해 Microsoft 365
keywords: Microsoft 365, 내부 위험 관리, 위험 관리, 규정 준수
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416482"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="2c131-104">내부자 위험 관리 알림 템플릿</span><span class="sxs-lookup"><span data-stu-id="2c131-104">Insider risk management notice templates</span></span>

<span data-ttu-id="2c131-105">내부자 위험 관리 알림 템플릿을 사용하면 활동으로 정책 일치 및 경고가 생성될 때 사용자에게 전자 메일 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="2c131-106">대부분의 경우 경고를 생성하는 사용자 작업은 잘못되거나 의도하지 않은 활동의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="2c131-107">알림은 사용자에게 더 주의를 들이고 재교육을 위한 정보 링크 또는 회사 정책 리소스에 대한 링크를 제공해야 하는 간단한 미리 알림 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="2c131-108">알림은 내부 규정 준수 교육 프로그램의 중요한 부분일 수 있으며, 재발하는 위험 활동을 하는 사용자를 위해 문서화된 감사 내선 정보를 만드는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="2c131-109">문제 해결 프로세스의 일부로 정책 일치에 대한 전자 메일 미리 알림 알림을 사용자에게 보내고 싶은 경우 알림 템플릿을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="2c131-110">검토할 특정 경고와 연결된 사용자 전자 메일 주소로만 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="2c131-111">정책 일치에 적용할 알림 템플릿을 선택할 때 템플릿에 정의된 필드 값을 수락하거나 필요한 경우 필드를 덮어 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="2c131-112">알림 서식 파일 대시보드</span><span class="sxs-lookup"><span data-stu-id="2c131-112">Notice templates dashboard</span></span>

<span data-ttu-id="2c131-113">**알림 템플릿 대시보드** 에 구성된 알림 템플릿 목록이 표시되고 새 알림 템플릿을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="2c131-114">알림 템플릿은 가장 최근의 알림 템플릿이 먼저 나열되는 역 날짜 순서로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![내부자 위험 관리 알림 서식 파일 대시보드](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="2c131-116">알림용 HTML</span><span class="sxs-lookup"><span data-stu-id="2c131-116">HTML for notices</span></span>

<span data-ttu-id="2c131-117">알림에 대해 간단한 텍스트 기반 전자 메일 메시지를 만드는 것보다 더 자세한 메시지를 만들 경우 알림 템플릿의 메시지 본문 필드에 HTML을 사용하여 보다 자세한 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="2c131-118">다음 예에서는 기본 HTML 기반 전자 메일 알림 템플릿에 대한 메시지 본문 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

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
> <span data-ttu-id="2c131-119">내부자 위험 관리 알림 템플릿의 HTML href 특성 구현에서는 현재 URL 참조에 대한 두 번의 인용 부호 대신 단일 인용 부호만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="2c131-120">새 알림 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="2c131-120">Create a new notice template</span></span>

<span data-ttu-id="2c131-121">새 내부자 위험 관리 알림 템플릿을 만들기 위해  내부자 위험 관리 솔루션의 알림 마법사를 사용하여 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="2c131-122">다음 단계를 완료하여 새 내부자 위험 관리 알림 템플릿을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="2c131-123">규정 [Microsoft 365 센터에서](https://compliance.microsoft.com)내부자 위험 관리로 **이동하여** 알림 템플릿 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="2c131-124">알림 **서식 파일 만들기를 선택하여** 알림 마법사를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="2c131-125">새 알림 **서식 파일 만들기 페이지에서** 다음 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="2c131-126">**서식 파일 이름:** 알림의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="2c131-127">이 이름은 사례에서 통지를 보낼 때 알림 대시보드의 알림 목록 및 알림 선택 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="2c131-128">**보낸 사람:** 알림의 보낸 사람 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="2c131-129">이 주소는 사례에서 통지를 보낼 때 변경되지 않는 한 사용자에게 전송된 모든 알림의 **보낸사서:** 필드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="2c131-130">**Cc 및 Bcc** 필드: 선택적 사용자 또는 그룹이 구독의 Active Directory에서 선택한 정책 일치를 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="2c131-131">**제목:** 메시지의 제목 줄에 나타나는 정보로, 텍스트 문자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="2c131-132">**메시지 본문:** 메시지 본문에 나타나는 정보로, 텍스트 또는 HTML 값을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="2c131-133">**만들기를** 선택하여 알림 서식 파일을  만들고 저장하거나 취소를 선택하여 알림 서식 파일을 저장하지 않고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="2c131-134">알림 서식 파일 업데이트</span><span class="sxs-lookup"><span data-stu-id="2c131-134">Update a notice template</span></span>

<span data-ttu-id="2c131-135">기존 내부자 위험 관리 알림 템플릿을 업데이트하기 위해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="2c131-136">규정 [Microsoft 365 센터에서](https://compliance.microsoft.com)내부자 위험 관리로 **이동하여** 알림 템플릿 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="2c131-137">알림 대시보드에서 관리할 알림 서식 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="2c131-138">알림 세부 정보 페이지에서 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c131-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="2c131-139">편집 **페이지에서** 다음 필드를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="2c131-140">**서식 파일 이름:** 알림의 새 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="2c131-141">이 이름은 사례에서 통지를 보낼 때 알림 대시보드의 알림 목록 및 알림 선택 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="2c131-142">**보낸 사람:** 알림의 보낸 사람 전자 메일 주소를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="2c131-143">이 주소는 사례에서 통지를 보낼 때 변경되지 않는 한 사용자에게 전송된 모든 알림의 **보낸사서:** 필드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="2c131-144">**Cc 및 Bcc** 필드: 선택적 사용자 또는 그룹을 업데이트하여 구독에 대한 Active Directory에서 선택한 정책 일치에 대한 알림을 하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="2c131-145">**제목:** 메시지의 제목 줄에 나타나는 정보를 업데이트하고 텍스트 문자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="2c131-146">**메시지 본문:** 메시지 본문에 나타나고 텍스트 또는 HTML 값을 지원하는 정보를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="2c131-147">**저장을** 선택하여 알림 업데이트 및  저장을 선택하거나 취소를 선택하여 알림 서식 파일을 저장하지 않고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="2c131-148">알림 서식 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="2c131-148">Delete a notice template</span></span>

<span data-ttu-id="2c131-149">기존 내부자 위험 관리 알림 템플릿을 삭제하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="2c131-150">규정 [Microsoft 365 센터에서](https://compliance.microsoft.com)내부자 위험 관리로 **이동하여** 알림 템플릿 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="2c131-151">알림 대시보드에서 삭제할 알림 서식 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="2c131-152">도구 **모음에서** 삭제 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="2c131-153">알림 서식 파일을 삭제하려면 **삭제** 대화 상자에서 예를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c131-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="2c131-154">지우기 작업을 취소하려면 취소 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c131-154">To cancel the deletion, select **Cancel**.</span></span>
