---
title: 끝점용 Microsoft Defender를 통해 검사 예약 방법(Linux)
description: 조직의 자산을 보다 잘 보호하기 위해 끝점용 Microsoft Defender(Linux)에 대한 자동 검사 시간을 예약하는 방법을 학습합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 검사, 바이러스 백신, 끝점용 Microsoft Defender(linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f868570fccf9b30cde5f16aa8e71292fb8b09497
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933136"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="47656-104">끝점용 Microsoft Defender를 통해 검사 예약(Linux)</span><span class="sxs-lookup"><span data-stu-id="47656-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="47656-105">Linux에 대한 검색을 실행하기 위해 [지원되는 명령을 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)</span><span class="sxs-lookup"><span data-stu-id="47656-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="47656-106">Linux(및 Unix)에는 예약된 작업을 실행할 수 있는 **크로ntab(작업** 스케줄러와 유사)라는 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="47656-107">필수 조건</span><span class="sxs-lookup"><span data-stu-id="47656-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="47656-108">모든 표준 시간대 목록을 얻습니다. 다음 명령을 실행합니다. `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="47656-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="47656-109">타임존의 예:</span><span class="sxs-lookup"><span data-stu-id="47656-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="47656-110">Cron 작업을 설정하는 경우</span><span class="sxs-lookup"><span data-stu-id="47656-110">To set the Cron job</span></span>
<span data-ttu-id="47656-111">다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-111">Use the following commands:</span></span>

<span data-ttu-id="47656-112">**크로ntab 항목을 백업하는 경우**</span><span class="sxs-lookup"><span data-stu-id="47656-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="47656-113">여기서 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="47656-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="47656-114">편집하거나 제거하기 전에 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="47656-115">크로ntab를 편집하고 루트 사용자로 새 작업을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="47656-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="47656-116">기본 편집기는 VIM입니다.</span><span class="sxs-lookup"><span data-stu-id="47656-116">The default editor is VIM.</span></span>

<span data-ttu-id="47656-117">다음이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-117">You might see:</span></span>

<span data-ttu-id="47656-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="47656-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="47656-119">"Insert" 누르기</span><span class="sxs-lookup"><span data-stu-id="47656-119">Press “Insert”</span></span>

<span data-ttu-id="47656-120">다음 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-120">Add the following entries:</span></span>

<span data-ttu-id="47656-121">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="47656-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="47656-122">0 2 \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="47656-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="47656-123">이 예제에서는 이 예제를 00분, 2시로 설정하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47656-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="47656-124">(24시간 형식의 시간), 월의 모든 일, 모든 월, 토요일</span><span class="sxs-lookup"><span data-stu-id="47656-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="47656-125">즉, 토요일은 토요일 오후 2시에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="47656-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="47656-126">태평양(UTC -8).</span><span class="sxs-lookup"><span data-stu-id="47656-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="47656-127">"Esc" 누르기</span><span class="sxs-lookup"><span data-stu-id="47656-127">Press “Esc”</span></span>

<span data-ttu-id="47656-128">따옴표 없이 ":wq"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="47656-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="47656-129">w == write, q == quit</span></span>

<span data-ttu-id="47656-130">크로인 작업을 보시고 입력합니다. `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="47656-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="47656-132">**크론 작업 실행을 검사하기 위해**</span><span class="sxs-lookup"><span data-stu-id="47656-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="47656-133">**mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="47656-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="47656-134">Ansible, 정적 또는 Puppet을 사용하는 사람</span><span class="sxs-lookup"><span data-stu-id="47656-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="47656-135">다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="47656-136">Ansible에서 크론 작업을 설정</span><span class="sxs-lookup"><span data-stu-id="47656-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="47656-137">자세한 내용은 [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="47656-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="47656-138">To set crontabs in아이프리드</span><span class="sxs-lookup"><span data-stu-id="47656-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="47656-139">자세한 내용은 [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="47656-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="47656-140">Puppet에서 크론 작업을 설정하는 경우</span><span class="sxs-lookup"><span data-stu-id="47656-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="47656-141">자원 유형: cron</span><span class="sxs-lookup"><span data-stu-id="47656-141">Resource Type: cron</span></span>

<span data-ttu-id="47656-142">자세한 내용은 [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="47656-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="47656-143">Puppet으로 자동화: Cron 작업 및 예약된 작업</span><span class="sxs-lookup"><span data-stu-id="47656-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="47656-144">자세한 내용은 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="47656-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="47656-145">추가 정보</span><span class="sxs-lookup"><span data-stu-id="47656-145">Additional information</span></span>

<span data-ttu-id="47656-146">**크로ntab에 대한 도움말을 얻은 경우**</span><span class="sxs-lookup"><span data-stu-id="47656-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="47656-147">**현재 사용자의 크로ntab 파일 목록을 얻은 경우**</span><span class="sxs-lookup"><span data-stu-id="47656-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="47656-148">**다른 사용자의 크로ntab 파일 목록을 얻은 경우**</span><span class="sxs-lookup"><span data-stu-id="47656-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="47656-149">**크로ntab 항목을 백업하는 경우**</span><span class="sxs-lookup"><span data-stu-id="47656-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="47656-150">편집하거나 제거하기 전에 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="47656-151">**크로ntab 항목을 복원하는 경우**</span><span class="sxs-lookup"><span data-stu-id="47656-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="47656-152">**크로ntab를 편집하고 루트 사용자로 새 작업을 추가하려면**</span><span class="sxs-lookup"><span data-stu-id="47656-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="47656-153">**크로ntab를 편집하고 새 작업을 추가하려면**</span><span class="sxs-lookup"><span data-stu-id="47656-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="47656-154">**다른 사용자의 크로ntab 항목을 편집하려면**</span><span class="sxs-lookup"><span data-stu-id="47656-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="47656-155">**모든 크로ntab 항목을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="47656-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="47656-156">**다른 사용자의 크로ntab 항목을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="47656-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="47656-157">**설명**</span><span class="sxs-lookup"><span data-stu-id="47656-157">**Explanation**</span></span>

<span data-ttu-id="47656-158">+—————- 분(값: 0 – 59)(특수 문자: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="47656-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="47656-159">| +————- 시간(값: 0 – 23)(특수 문자: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="47656-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="47656-160">| | +———-(값: 1 ~ 31)(특수 문자: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="47656-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="47656-161">| | | +——- 월(값: 1 ~ 12)(특수 문자: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="47656-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="47656-162">| | | | +-- 주중(값: 0 - 6)(Sunday=0 또는 7)(특수 문자: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="47656-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="47656-163">| | | | |\*\*\*\*\*명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47656-163">| | | | |\*\*\*\*\*command to be executed</span></span>


