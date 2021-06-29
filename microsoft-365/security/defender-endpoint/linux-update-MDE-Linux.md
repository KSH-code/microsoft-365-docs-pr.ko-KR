---
title: 끝점용 Microsoft Defender 업데이트를 예약하는 방법(Linux)
description: 조직의 자산을 보다 잘 보호하기 위해 끝점용 Microsoft Defender(Linux)의 업데이트를 예약하는 방법을 배워야 합니다.
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
ms.openlocfilehash: 7ebb37e80cae0e9dd70d01600c47bd1459c122c3
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194904"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="fa6c3-104">엔드포인트용 Microsoft Defender(Linux) 업데이트 예약</span><span class="sxs-lookup"><span data-stu-id="fa6c3-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="fa6c3-105">Linux의 끝점용 Microsoft Defender에서 업데이트를 실행하기 위해 Linux에서 [끝점용 Microsoft Defender 업데이트 배포를 참조하세요.](/microsoft-365/security/defender-endpoint/linux-updates)</span><span class="sxs-lookup"><span data-stu-id="fa6c3-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="fa6c3-106">Linux(및 Unix)에는 예약된 작업을 실행할 수 있는 **크로ntab(작업** 스케줄러와 유사)라는 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="fa6c3-107">필수 조건</span><span class="sxs-lookup"><span data-stu-id="fa6c3-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="fa6c3-108">모든 표준 시간대 목록을 얻습니다. 다음 명령을 실행합니다. `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="fa6c3-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="fa6c3-109">타임존의 예:</span><span class="sxs-lookup"><span data-stu-id="fa6c3-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="fa6c3-110">Cron 작업을 설정하는 경우</span><span class="sxs-lookup"><span data-stu-id="fa6c3-110">To set the Cron job</span></span>
<span data-ttu-id="fa6c3-111">다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-111">Use the following commands:</span></span>

<span data-ttu-id="fa6c3-112">**크로ntab 항목을 백업하는 경우**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="fa6c3-113">여기서 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="fa6c3-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="fa6c3-114">편집하거나 제거하기 전에 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="fa6c3-115">크로ntab를 편집하고 루트 사용자로 새 작업을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="fa6c3-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="fa6c3-116">기본 편집기는 VIM입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-116">The default editor is VIM.</span></span>

<span data-ttu-id="fa6c3-117">다음이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-117">You might see:</span></span>

<span data-ttu-id="fa6c3-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="fa6c3-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="fa6c3-119">및</span><span class="sxs-lookup"><span data-stu-id="fa6c3-119">And</span></span>

<span data-ttu-id="fa6c3-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="fa6c3-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="fa6c3-121">끝점에 대한 [Microsoft Defender 검사 예약(Linux) 참조](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="fa6c3-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="fa6c3-122">"Insert" 누르기</span><span class="sxs-lookup"><span data-stu-id="fa6c3-122">Press “Insert”</span></span>

<span data-ttu-id="fa6c3-123">다음 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-123">Add the following entries:</span></span>

<span data-ttu-id="fa6c3-124">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="fa6c3-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="fa6c3-125">! RHEL 및 변형(CentOS 및 Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="fa6c3-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="fa6c3-126">! SLES 및 변형</span><span class="sxs-lookup"><span data-stu-id="fa6c3-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="fa6c3-127">! Ubuntu 및 데비안 시스템</span><span class="sxs-lookup"><span data-stu-id="fa6c3-127">!Ubuntu and Debian systems</span></span>

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="fa6c3-128">위의 예제에서는 일요일, 모든 월의 하루를 00분, 오후 6시(24시간 형식의 시간)로 설정하고 있습니다. [$(date + \% d) -le 15] == 15일(3주)보다 작거나 같지 않으면 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="fa6c3-129">즉, 이 매월 3일 일요일(7)은 매일 아침 6시에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="fa6c3-130">태평양(UTC -8).</span><span class="sxs-lookup"><span data-stu-id="fa6c3-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="fa6c3-131">"Esc" 누르기</span><span class="sxs-lookup"><span data-stu-id="fa6c3-131">Press “Esc”</span></span>

<span data-ttu-id="fa6c3-132">":wq"를 이중 따옴표로 w/o 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="fa6c3-133">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="fa6c3-133">w == write, q == quit</span></span>

<span data-ttu-id="fa6c3-134">크로인 작업을 보시고 입력합니다. `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="fa6c3-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="Linux의 끝점용 Defender 업데이트":::

<span data-ttu-id="fa6c3-136">크론 작업을 검사하기 위해 실행됩니다. `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="fa6c3-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="fa6c3-137">mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="fa6c3-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="fa6c3-138">Ansible, 정적 또는 Puppet을 사용하는 사람</span><span class="sxs-lookup"><span data-stu-id="fa6c3-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="fa6c3-139">다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="fa6c3-140">Ansible에서 크론 작업을 설정</span><span class="sxs-lookup"><span data-stu-id="fa6c3-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="fa6c3-141">자세한 내용은 [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="fa6c3-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="fa6c3-142">To set crontabs in아이프리드</span><span class="sxs-lookup"><span data-stu-id="fa6c3-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="fa6c3-143">자세한 내용은 [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="fa6c3-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="fa6c3-144">Puppet에서 크론 작업을 설정하는 경우</span><span class="sxs-lookup"><span data-stu-id="fa6c3-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="fa6c3-145">자원 유형: cron</span><span class="sxs-lookup"><span data-stu-id="fa6c3-145">Resource Type: cron</span></span>

<span data-ttu-id="fa6c3-146">자세한 내용은 [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="fa6c3-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="fa6c3-147">Puppet으로 자동화: Cron 작업 및 예약된 작업</span><span class="sxs-lookup"><span data-stu-id="fa6c3-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="fa6c3-148">자세한 내용은 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="fa6c3-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="fa6c3-149">추가 정보</span><span class="sxs-lookup"><span data-stu-id="fa6c3-149">Additional information</span></span>

<span data-ttu-id="fa6c3-150">**크로ntab에 대한 도움말을 얻은 경우**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="fa6c3-151">**현재 사용자의 크로ntab 파일 목록을 얻은 경우**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="fa6c3-152">**다른 사용자의 크로ntab 파일 목록을 얻은 경우**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="fa6c3-153">**크로ntab 항목을 백업하는 경우**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="fa6c3-154">편집하거나 제거하기 전에 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="fa6c3-155">**크로ntab 항목을 복원하는 경우**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="fa6c3-156">**크로ntab를 편집하고 루트 사용자로 새 작업을 추가하려면**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="fa6c3-157">**크로ntab를 편집하고 새 작업을 추가하려면**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="fa6c3-158">**다른 사용자의 크로ntab 항목을 편집하려면**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="fa6c3-159">**모든 크로ntab 항목을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="fa6c3-160">**다른 사용자의 크로ntab 항목을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="fa6c3-161">**설명**</span><span class="sxs-lookup"><span data-stu-id="fa6c3-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

