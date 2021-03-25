---
title: 랜섬웨어 공격으로부터 복구
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 관리자는 랜섬웨어 공격으로부터 복구하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 242a4a2f43bd91d75caeaeaa0488f23a5ba4319d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205764"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="9799d-103">Microsoft 365의 랜섬웨어 공격으로부터 복구</span><span class="sxs-lookup"><span data-stu-id="9799d-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9799d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="9799d-104">**Applies to**</span></span>
- [<span data-ttu-id="9799d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9799d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9799d-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="9799d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9799d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9799d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9799d-108">조직을 보호하기 위해 모든 예방 조치를 취하는 경우에도 여전히 랜섬웨어 공격의 피해가 될 [수](/windows/security/threat-protection/intelligence/ransomware-malware) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="9799d-109">랜섬웨어는 대기업에 있으며 공격은 매우 정교합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="9799d-110">이 문서의 단계는 데이터를 복구하고 내부 감염 확산을 중지할 수 있는 최상의 기회를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="9799d-111">시작하기 전에 다음 항목을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="9799d-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="9799d-112">대금을 지불하면 파일에 대한 액세스 권한이 반환된다고 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="9799d-113">실제로 대가를 지불하면 더 많은 랜섬웨어의 대상이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="9799d-114">이미 결제했지만 공격자 솔루션을 사용하지 않고 복구한 경우 은행에 문의하여 거래를 차단할 수 있는지 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="9799d-115">또한 랜섬웨어 공격을 법 집행 기관, 사기 보고 웹 사이트 및 Microsoft에 보고하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="9799d-116">공격과 그 결과에 신속하게 대응하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="9799d-117">대기 시간이 길면 영향을 받는 데이터를 복구할 가능성이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="9799d-118">1단계: 백업 확인</span><span class="sxs-lookup"><span data-stu-id="9799d-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="9799d-119">오프라인 백업이 있는 경우 환경에서 랜섬웨어  페이로드(맬웨어)를 제거한 후 암호화된 데이터를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="9799d-120">백업이 없는 경우 또는 백업이 랜섬웨어의 영향을 받은 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="9799d-121">2단계: Exchange ActiveSync 및 OneDrive 동기화를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9799d-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="9799d-122">여기서 핵심은 랜섬웨어에 의해 데이터 암호화의 확산을 중지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="9799d-123">전자 메일이 랜섬웨어 암호화의 대상으로 의심되는 경우 사서함에 대한 사용자 액세스를 일시적으로 사용하지 않도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="9799d-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="9799d-124">Exchange ActiveSync Exchange Online 사서함 간에 데이터를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="9799d-125">사서함에 Exchange ActiveSync 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [How to disable Exchange ActiveSync for users in Exchange Online을 참조하세요.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="9799d-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="9799d-126">다른 유형의 사서함 액세스를 사용하지 않도록 설정하는 경우 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="9799d-127">[사서함에 대해 MAPI를 사용하도록 설정하거나 사용하지 않도록 설정](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="9799d-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="9799d-128">사용자에 대해 POP3 또는 IMAP4 액세스 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9799d-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="9799d-129">OneDrive 동기화를 Pausing하면 잠재적으로 감염된 장치에 의해 클라우드 데이터가 업데이트되지 못하도록 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="9799d-130">자세한 내용은 [OneDrive에서 동기화를](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)일시 중지하고 다시 시작하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9799d-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="9799d-131">3단계: 영향을 받는 장치에서 맬웨어 제거</span><span class="sxs-lookup"><span data-stu-id="9799d-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="9799d-132">의심되는 모든 컴퓨터 및 장치에서 최신 바이러스 백신 검색을 실행하여 랜섬웨어와 연결된 페이로드를 검색하고 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="9799d-133">데이터를 동기화하는 장치 또는 매핑된 네트워크 드라이브의 대상을 검색하는 것을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9799d-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="9799d-134">또는 [(Windows Defender](https://www.microsoft.com/windows/comprehensive-security) [클라이언트의](https://www.microsoft.com/download/details.aspx?id=5201)경우) 를 사용하여 Microsoft Security Essentials.</span><span class="sxs-lookup"><span data-stu-id="9799d-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="9799d-135">랜섬웨어 또는 맬웨어를 제거하는 데 도움이 되는 [대안으로는 MSRT(악성](https://www.microsoft.com/download/details.aspx?id=9905)소프트웨어 제거 도구)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="9799d-136">이러한 옵션이 작동하지 않는 경우 오프라인으로 또는 맬웨어 [Windows Defender](https://support.microsoft.com/help/17466) 문제 해결을 시도할 [수 있습니다.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="9799d-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="9799d-137">4단계: 정리된 컴퓨터 또는 장치에서 파일 복구</span><span class="sxs-lookup"><span data-stu-id="9799d-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="9799d-138">사용자 환경에서 랜섬웨어 페이로드를 제거하기 위한 이전 단계를 완료한 후(랜섬웨어가 파일을 암호화하거나 제거하는 것을 방지) Windows 10 및 Windows 8.1의 파일 기록 또는 Windows 7의 시스템 보호를 사용하여 로컬 파일 및 폴더를 복구할 수 있습니다. [](https://support.microsoft.com/help/17128)</span><span class="sxs-lookup"><span data-stu-id="9799d-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="9799d-139">**참고:**</span><span class="sxs-lookup"><span data-stu-id="9799d-139">**Notes**:</span></span>

- <span data-ttu-id="9799d-140">일부 랜섬웨어는 또한 백업 버전을 암호화하거나 삭제하기 때문에 파일 기록 또는 시스템 보호를 사용하여 파일을 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="9799d-141">이 경우 다음 섹션에 설명된 바와 같이 랜섬웨어 또는 OneDrive의 영향을 받지 않는 외부 드라이브 또는 장치에서 백업을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="9799d-142">폴더가 OneDrive와 동기화된 경우 최신 버전의 Windows를 사용하지 않는 경우 파일 기록을 사용하는 데 몇 가지 제한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="9799d-143">5단계: 비즈니스용 OneDrive에서 파일 복구</span><span class="sxs-lookup"><span data-stu-id="9799d-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="9799d-144">비즈니스용 OneDrive에서 파일 복원을 사용하면 지난 30일 이내에 전체 OneDrive를 이전 시점으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="9799d-145">자세한 내용은 [OneDrive 복원을 참조하세요.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="9799d-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="9799d-146">6단계: 삭제된 전자 메일 복구</span><span class="sxs-lookup"><span data-stu-id="9799d-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="9799d-147">드물지만 랜섬웨어가 모든 전자 메일을 삭제한 경우 삭제된 항목을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="9799d-148">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9799d-148">For more information, see:</span></span>

- [<span data-ttu-id="9799d-149">사용자의 사서함에서 삭제된 메시지 복구</span><span class="sxs-lookup"><span data-stu-id="9799d-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="9799d-150">Windows용 Outlook에서 삭제된 항목 복구</span><span class="sxs-lookup"><span data-stu-id="9799d-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="9799d-151">7단계: Exchange ActiveSync 및 OneDrive 동기화 다시 활성화</span><span class="sxs-lookup"><span data-stu-id="9799d-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="9799d-152">컴퓨터와 장치를 정리하고 데이터를 복구한 후 이전에 [2단계에서](#step-2-disable-exchange-activesync-and-onedrive-sync)사용하지 않도록 Exchange ActiveSync 및 OneDrive 동기화를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="9799d-153">8단계(선택 사항): 특정 파일 확장명에 대한 OneDrive 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="9799d-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="9799d-154">복구한 후 비즈니스용 OneDrive 클라이언트가 이 랜섬웨어의 영향을 받은 파일 형식을 동기화하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="9799d-155">자세한 내용은 [Set-SPOTenantSyncClientRestriction을 참조하세요.](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="9799d-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="9799d-156">공격 보고</span><span class="sxs-lookup"><span data-stu-id="9799d-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="9799d-157">연락 사법 기관</span><span class="sxs-lookup"><span data-stu-id="9799d-157">Contact law enforcement</span></span>

<span data-ttu-id="9799d-158">현지 또는 연방 사법 기관에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="9799d-159">예를 들어 미국에 있는 경우 [FBI](https://www.fbi.gov/contact-us/field)현지 현장 사무실, [IC3](http://www.ic3.gov/complaint/default.aspx) 또는 비밀 서비스에 [문의할 수 있습니다.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="9799d-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="9799d-160">국가의 사기 보고 웹 사이트에 보고서 제출</span><span class="sxs-lookup"><span data-stu-id="9799d-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="9799d-161">사기 보고 웹 사이트는 사기를 방지하고 방지하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="9799d-162">또한 사기를 당했다고 보고하는 메커니즘도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="9799d-163">오스트레일리아: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="9799d-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="9799d-164">캐나다: [캐나다의 사기 방지 센터](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="9799d-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="9799d-165">프랑스: [기관 국가 de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="9799d-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="9799d-166">독일: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="9799d-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="9799d-167">아일랜드: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="9799d-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="9799d-168">뉴질랜드: [소비자 업무 사기](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="9799d-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="9799d-169">영국: [작업 사기](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="9799d-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="9799d-170">미국: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="9799d-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="9799d-171">해당 국가가 목록에 없는 경우 현지 또는 연방 법 집행 기관에 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="9799d-172">Microsoft에 전자 메일 메시지 제출</span><span class="sxs-lookup"><span data-stu-id="9799d-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="9799d-173">여러 방법 중 하나를 사용하여 랜섬웨어가 포함된 피싱 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="9799d-174">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9799d-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9799d-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9799d-175">See also</span></span>

- [<span data-ttu-id="9799d-176">랜섬웨어</span><span class="sxs-lookup"><span data-stu-id="9799d-176">Ransomware</span></span>](/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="9799d-177">랜섬웨어 대응 - 지불할지 또는 지불하지 않을 것인가?</span><span class="sxs-lookup"><span data-stu-id="9799d-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="9799d-178">Norsk 지수는 투명성을 통해 랜섬웨어 공격에 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="9799d-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="9799d-179">OneDrive에서 랜섬웨어 검색 및 파일 복구</span><span class="sxs-lookup"><span data-stu-id="9799d-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="9799d-180">Microsoft 보안 인텔리전스 보고서</span><span class="sxs-lookup"><span data-stu-id="9799d-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="9799d-181">Office 파일에서 매크로 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9799d-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="9799d-182">EOP 및 Office 365용 Microsoft Defender 보안에 대한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="9799d-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

- [<span data-ttu-id="9799d-183">업그레이드 가치가 있는 업그레이드: Windows 10의 차세대 보안은 2017년 랜섬웨어 발생에 대한 탄력적인 증명</span><span class="sxs-lookup"><span data-stu-id="9799d-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="9799d-184">No mas, Samas: What's in this ransomware's modus operandi?</span><span class="sxs-lookup"><span data-stu-id="9799d-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="9799d-185">잠긴 맬웨어, 피하기 다행히</span><span class="sxs-lookup"><span data-stu-id="9799d-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="9799d-186">MSRT 2016년 7월: Cerber 랜섬웨어</span><span class="sxs-lookup"><span data-stu-id="9799d-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="9799d-187">Cerberus와 같은 Cerber 랜섬웨어의 세 헤드</span><span class="sxs-lookup"><span data-stu-id="9799d-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="9799d-188">(the) Da Vinci 코드의 영향을 미치는 Troldesh 랜섬웨어</span><span class="sxs-lookup"><span data-stu-id="9799d-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)