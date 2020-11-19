---
title: 랜섬웨어 공격으로부터 복구
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365 관리자는 랜 섬 웨어 공격 으로부터 복구 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: a1369e64821902e3c2a3061acd1bbebeeb6c85ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357100"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="9bb4c-103">Microsoft 365에서 랜 섬 웨어 공격 으로부터 복구</span><span class="sxs-lookup"><span data-stu-id="9bb4c-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9bb4c-104">조직을 보호 하기 위해 모든 예방책을 사용 하는 경우에도 여전히 [랜 섬 웨어](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 공격을 막을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="9bb4c-105">랜 섬 웨어는 대규모 비즈니스로, 공격은 매우 정교 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-105">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="9bb4c-106">이 문서에서 설명 하는 단계에서는 데이터를 복구 하 고 감염의 내부 확산을 중지할 수 있는 최상의 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-106">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="9bb4c-107">시작하기 전에 다음 항목을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="9bb4c-108">Ransom의 비용을 지불 하면 파일에 대 한 액세스 권한이 반환 된다는 보장이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="9bb4c-109">실제로 ransom를 지불할 경우 더 많은 랜 섬 웨어를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-109">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="9bb4c-110">이미 지불 되었지만 공격자의 솔루션을 사용 하지 않고 복구 한 경우에는 해당 은행에 연락 하 여 트랜잭션을 차단할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-110">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="9bb4c-111">또한이 문서 뒷부분에 설명 된 대로, 섬 웨어 공격을 법 집행, 사기 보고 웹 사이트 및 Microsoft에 보고 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="9bb4c-112">공격에 빠르게 응답 하 고 그 결과를 처리 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-112">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="9bb4c-113">기다리는 시간이 길수록 영향을 받는 데이터를 복구할 수 있다는 것을 덜 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="9bb4c-114">1 단계: 백업 확인</span><span class="sxs-lookup"><span data-stu-id="9bb4c-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="9bb4c-115">오프 라인 백업이 있는 경우 환경에서 맬웨어 (랜 섬 웨어 페이로드)를 제거한 **후** 에 암호화 된 데이터를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="9bb4c-116">백업이 없거나 해당 백업이 랜 섬 웨어의 영향을 받는 경우에는이 단계를 건너뛰어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="9bb4c-117">2 단계: Exchange ActiveSync 및 OneDrive 동기화 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="9bb4c-117">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="9bb4c-118">여기서 중요 한 점은 랜 섬 웨어에의 한 데이터 암호화 확산을 중지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="9bb4c-119">전자 메일이 랜 섬 웨어 암호화의 대상으로 의심 되는 경우 사서함에 대 한 사용자 액세스를 일시적으로 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-119">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="9bb4c-120">Exchange ActiveSync는 장치와 Exchange Online 사서함 간에 데이터를 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-120">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="9bb4c-121">사서함에 대해 Exchange ActiveSync를 사용 하지 않도록 설정 하려면 [Exchange Online에서 사용자에 대해 Exchange activesync를 사용 하지 않도록 설정 하는 방법을](https://support.microsoft.com/help/2795303)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-121">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="9bb4c-122">사서함에 대 한 다른 유형의 액세스를 사용 하지 않도록 설정 하려면 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="9bb4c-123">[사서함에 대해 MAPI를 사용 하거나 사용 하지 않도록](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="9bb4c-124">사용자에 대해 POP3 또는 IMAP4 액세스를 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9bb4c-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="9bb4c-125">OneDrive 동기화를 일시 중지 하면 잠재적으로 감염 된 장치에 의해 클라우드 데이터가 업데이트 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="9bb4c-126">자세한 내용은 [OneDrive에서 동기화 일시 중지 및 다시 시작 하는 방법을](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="9bb4c-127">3 단계: 영향을 받는 장치에서 맬웨어 제거</span><span class="sxs-lookup"><span data-stu-id="9bb4c-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="9bb4c-128">의심 되는 모든 컴퓨터 및 장치에 대해 최신 바이러스 백신 검사를 실행 하 여 랜 섬 웨어와 연결 된 페이로드를 검색 하 고 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-128">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="9bb4c-129">데이터를 동기화 하는 장치를 검색 하거나 매핑된 네트워크 드라이브의 대상을 잊어 버리는 것은 잊지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-129">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="9bb4c-130">[Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 또는 (이전 클라이언트용) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="9bb4c-131">랜 섬 웨어 또는 맬웨어를 제거 하는 데 도움이 되는 또 다른 방법은 [악성 소프트웨어 제거 도구 (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="9bb4c-132">이러한 옵션이 작동 하지 않으면 [Windows Defender offline](https://support.microsoft.com/help/17466) 을 시도 하거나 [맬웨어 검색 및 제거 문제를 해결할](https://support.microsoft.com/help/4466982)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="9bb4c-133">4 단계: 치료 된 컴퓨터 또는 장치에서 파일 복구</span><span class="sxs-lookup"><span data-stu-id="9bb4c-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="9bb4c-134">이전 단계를 완료 하 여 환경에서 랜 섬 웨어 페이로드를 제거한 후 (섬 웨어 파일을 암호화 하거나 제거 하지 못하게 함) windows 10 및 Windows 8.1의 [파일 기록을](https://support.microsoft.com/help/17128) 사용 하 여 로컬 파일 및 폴더 복구를 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="9bb4c-135">**참고:**</span><span class="sxs-lookup"><span data-stu-id="9bb4c-135">**Notes**:</span></span>

- <span data-ttu-id="9bb4c-136">일부 랜 섬 웨어도 백업 버전을 암호화 하거나 삭제 하므로 파일 기록 또는 시스템 보호를 사용 하 여 파일을 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="9bb4c-137">이 경우 다음 섹션에 설명 된 대로 랜 섬 웨어 또는 OneDrive의 영향을 받지 않았던 외부 드라이브 또는 장치에서 백업을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="9bb4c-138">폴더가 OneDrive에 동기화 되 고 최신 버전의 Windows를 사용 하지 않는 경우 파일 히스토리를 사용 하 여 몇 가지 제한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="9bb4c-139">5 단계: 비즈니스용 OneDrive에서 파일 복구</span><span class="sxs-lookup"><span data-stu-id="9bb4c-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="9bb4c-140">비즈니스용 OneDrive의 파일 복원 기능을 사용 하면 지난 30 일 이내에 이전 시점으로 전체 OneDrive를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="9bb4c-141">자세한 내용은 [OneDrive 복원을](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="9bb4c-142">6 단계: 삭제 된 전자 메일 복구</span><span class="sxs-lookup"><span data-stu-id="9bb4c-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="9bb4c-143">드물지만 랜 섬 웨어가 모든 전자 메일을 삭제 한 경우에는 삭제 된 항목을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="9bb4c-144">자세한 내용은 다음을 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-144">For more information, see:</span></span>

- [<span data-ttu-id="9bb4c-145">사용자의 사서함에서 삭제된 메시지 복구</span><span class="sxs-lookup"><span data-stu-id="9bb4c-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="9bb4c-146">Windows용 Outlook에서 삭제된 항목 복구</span><span class="sxs-lookup"><span data-stu-id="9bb4c-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="9bb4c-147">7 단계: Exchange ActiveSync 및 OneDrive 동기화 다시 사용</span><span class="sxs-lookup"><span data-stu-id="9bb4c-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="9bb4c-148">컴퓨터 및 장치를 청소 하 고 데이터를 복구한 후에는 [2 단계](#step-2-disable-exchange-activesync-and-onedrive-sync)에서 이전에 사용 하지 않도록 설정한 Exchange ActiveSync 및 OneDrive 동기화를 다시 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-148">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="9bb4c-149">8 단계 (선택 사항): 특정 파일 확장명에 대 한 OneDrive 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="9bb4c-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="9bb4c-150">복구한 후에는 비즈니스용 OneDrive 클라이언트에서이 랜 섬에 영향을 받은 파일 형식을 동기화 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="9bb4c-151">자세한 내용은 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="9bb4c-152">공격 보고</span><span class="sxs-lookup"><span data-stu-id="9bb4c-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="9bb4c-153">담당자 법률 집행</span><span class="sxs-lookup"><span data-stu-id="9bb4c-153">Contact law enforcement</span></span>

<span data-ttu-id="9bb4c-154">지역 또는 연방 법 집행 기관에 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="9bb4c-155">예를 들어 미국에 있는 경우 [FBI 로컬 필드인 office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) 또는 [Secret Service](http://www.secretservice.gov/)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="9bb4c-156">해당 국가의 사기 보고 웹 사이트로 보고서 제출</span><span class="sxs-lookup"><span data-stu-id="9bb4c-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="9bb4c-157">사기 보고 웹 사이트는 사기를 방지 하 고 방지 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="9bb4c-158">또한 사기가 피해자 인지 여부를 보고 하는 메커니즘도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="9bb4c-159">오스트레일리아: [Scamwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="9bb4c-160">캐나다: [캐나다 사기 방지 센터](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="9bb4c-161">프랑스: [agence de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="9bb4c-162">독일: [Bundesamt Für Sicherheit in Der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="9bb4c-163">아일랜드: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="9bb4c-164">뉴질랜드: 소비자에 게 [사기](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="9bb4c-165">영국: [작업 사기](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="9bb4c-166">미국: [온라인 보호 설정](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="9bb4c-167">해당 국가가 나열 되지 않으면 지역 또는 연방 법 집행 기관에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="9bb4c-168">Microsoft로 전자 메일 메시지 제출</span><span class="sxs-lookup"><span data-stu-id="9bb4c-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="9bb4c-169">몇 가지 방법 중 하나를 사용 하 여 랜 섬 웨어가 포함 된 피싱 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-169">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="9bb4c-170">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bb4c-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bb4c-171">See also</span></span>

- [<span data-ttu-id="9bb4c-172">랜</span><span class="sxs-lookup"><span data-stu-id="9bb4c-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="9bb4c-173">랜 섬 웨어 응답-비용 청구 또는 결제 안 하나요?</span><span class="sxs-lookup"><span data-stu-id="9bb4c-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="9bb4c-174">Norsk Hydro 투명도를 사용한 랜 섬 웨어 공격에 응답</span><span class="sxs-lookup"><span data-stu-id="9bb4c-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="9bb4c-175">랜 섬 웨어 검색 및 OneDrive에서 파일 복구</span><span class="sxs-lookup"><span data-stu-id="9bb4c-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="9bb4c-176">Microsoft 보안 인텔리전스 보고서</span><span class="sxs-lookup"><span data-stu-id="9bb4c-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="9bb4c-177">Office 파일에서 매크로를 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9bb4c-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="9bb4c-178">EOP 및 Office 용 Microsoft Defender 365 보안에 대 한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="9bb4c-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="9bb4c-179">훌륭한 업그레이드: Windows 10의 차세대 보안은 2017에서 랜 섬 웨어에 대 한 복원성을 입증 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="9bb4c-180">Ma 없음, Samas:이 랜 섬 웨어의 modus 기능 andi</span><span class="sxs-lookup"><span data-stu-id="9bb4c-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="9bb4c-181">Locky 맬웨어, 피하는 운이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb4c-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="9bb4c-182">MSRT 7 월 2016 일: (으)</span><span class="sxs-lookup"><span data-stu-id="9bb4c-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="9bb4c-183">Cerberus의 세 가지 헤드</span><span class="sxs-lookup"><span data-stu-id="9bb4c-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="9bb4c-184">Da 다빈치 코드의 영향을 받은 Troldesh 랜 섬 웨어</span><span class="sxs-lookup"><span data-stu-id="9bb4c-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
