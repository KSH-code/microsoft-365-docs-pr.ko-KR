---
title: 함께 개선 - Microsoft Defender 바이러스 백신 및 Office 365(OneDrive 포함) - 랜섬웨어 및 사이버 위협으로부터 더 나은 보호
description: OneDrive를 포함하는 Office 365는 Microsoft Defender 바이러스 백신과 잘 어울리게 함께 사용할 수 있습니다. 자세한 내용은 이 문서를 읽어 보아야 합니다.
keywords: windows defender, 바이러스 백신, office 365, onedrive, 복원, 랜섬웨어
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 41f22375aa117ba617eae59d4b8e9f8bb15ad4f0
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764102"
---
# <a name="better-together-microsoft-defender-antivirus-and-office-365"></a><span data-ttu-id="50b3d-105">함께 사용: Microsoft Defender 바이러스 백신 및 Office 365</span><span class="sxs-lookup"><span data-stu-id="50b3d-105">Better together: Microsoft Defender Antivirus and Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50b3d-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="50b3d-106">**Applies to:**</span></span>
- <span data-ttu-id="50b3d-107">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="50b3d-107">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>
- <span data-ttu-id="50b3d-108">Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="50b3d-108">Microsoft Defender Antivirus</span></span>
- <span data-ttu-id="50b3d-109">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50b3d-109">Microsoft 365</span></span>

<span data-ttu-id="50b3d-110">이미 다음을 알고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-110">You might already know that:</span></span>

- <span data-ttu-id="50b3d-111">**Microsoft Defender 바이러스 백신은 바이러스, 맬웨어** 및 스파이웨어와 같은 소프트웨어 위협으로부터 Windows 10 장치를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-111">**Microsoft Defender Antivirus protects your Windows 10 device from software threats, such as viruses, malware, and spyware**.</span></span> <span data-ttu-id="50b3d-112">Microsoft Defender 바이러스 백신은 Windows 10에 기본 제공되는 완전한 지속적인 보호 기능으로, 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-112">Microsoft Defender Antivirus is your complete, ongoing protection, built into Windows 10 and ready to go.</span></span> <span data-ttu-id="50b3d-113">[Microsoft Defender 바이러스 백신은 차세대 보호입니다.](./microsoft-defender-antivirus-in-windows-10.md)</span><span class="sxs-lookup"><span data-stu-id="50b3d-113">[Microsoft Defender Antivirus is your next-generation protection](./microsoft-defender-antivirus-in-windows-10.md).</span></span> 

- <span data-ttu-id="50b3d-114">**Office 365에는** 피싱 방지, 스패마 방지 및 맬웨어 방지 보호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-114">**Office 365 includes antiphishing, antispam, and antimalware protection**.</span></span> <span data-ttu-id="50b3d-115">Office 365 구독을 사용하면 프리미엄 전자 메일 및 일정, Office 앱, 1 TB의 클라우드 저장소(OneDrive를 통해) 및 모든 장치에서 고급 보안을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-115">With your Office 365 subscription, you get premium email and calendars, Office apps, 1 TB of cloud storage (via OneDrive), and advanced security across all your devices.</span></span> <span data-ttu-id="50b3d-116">가정용 및 비즈니스 사용자도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-116">This is true for home and business users.</span></span> <span data-ttu-id="50b3d-117">또한 비즈니스 사용자인 경우 조직에서 Office 365 E5를 사용하는 경우 Office 365를 사용하여 위협으로부터 보호하는 Microsoft Defender for Office 365를 통해 훨씬 더 많은 [보호를](/microsoft-365/security/office-365-security/protect-against-threats)얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-117">And if you're a business user, and your organization is using Office 365 E5, you get even more protection through Microsoft Defender for Office 365 [Protect against threats with Office 365](/microsoft-365/security/office-365-security/protect-against-threats).</span></span>

- <span data-ttu-id="50b3d-118">**Office 365에 포함된 OneDrive를** 사용하면 온라인으로 파일 및 폴더를 저장하고 적합한 폴더를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-118">**OneDrive, included in Office 365, enables you to store your files and folders online, and share them as you see fit**.</span></span> <span data-ttu-id="50b3d-119">OneDrive에 저장된 공동 작업 파일 및 사용자와 함께 작업할 수 있습니다(업무 또는 즐거움을 위해).</span><span class="sxs-lookup"><span data-stu-id="50b3d-119">You can work together with people (for work or fun), and coauthor files that are stored in OneDrive.</span></span> <span data-ttu-id="50b3d-120">모든 장치(PC, 휴대폰 및 태블릿)에서 파일에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-120">You can also access your files across all your devices (your PC, phone, and tablet).</span></span> <span data-ttu-id="50b3d-121">[OneDrive에서](/OneDrive/manage-sharing)공유 관리</span><span class="sxs-lookup"><span data-stu-id="50b3d-121">[Manage sharing in OneDrive](/OneDrive/manage-sharing).</span></span>

<span data-ttu-id="50b3d-122">**그러나 Office 365와** 함께 Microsoft Defender 바이러스 백신을 사용할 수 있는 좋은 보안 이유가 있나요?</span><span class="sxs-lookup"><span data-stu-id="50b3d-122">**But did you know there are good security reasons to use Microsoft Defender Antivirus together with Office 365**?</span></span> <span data-ttu-id="50b3d-123">다음은 두 가지 지원 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-123">Here are two:</span></span>

 1. <span data-ttu-id="50b3d-124">[랜섬웨어 보호 및 복구를 받을 수 있습니다.](#ransomware-protection-and-recovery)</span><span class="sxs-lookup"><span data-stu-id="50b3d-124">[You get ransomware protection and recovery](#ransomware-protection-and-recovery).</span></span>

 2. <span data-ttu-id="50b3d-125">[통합은 더 나은 보호를 의미 합니다.](#integration-means-better-protection)</span><span class="sxs-lookup"><span data-stu-id="50b3d-125">[Integration means better protection](#integration-means-better-protection).</span></span>

<span data-ttu-id="50b3d-126">자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50b3d-126">Read the following sections to learn more.</span></span>

## <a name="ransomware-protection-and-recovery"></a><span data-ttu-id="50b3d-127">랜섬웨어 보호 및 복구</span><span class="sxs-lookup"><span data-stu-id="50b3d-127">Ransomware protection and recovery</span></span>

<span data-ttu-id="50b3d-128">[파일을 OneDrive에](/onedrive)저장하고 [Microsoft Defender 바이러스](./microsoft-defender-antivirus-in-windows-10.md) 백신이 장치에서 랜섬웨어 위협을 감지하면 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-128">When you save your files to [OneDrive](/onedrive), and [Microsoft Defender Antivirus](./microsoft-defender-antivirus-in-windows-10.md) detects a ransomware threat on your device, the following things occur:</span></span>

1. <span data-ttu-id="50b3d-129">**위협에 대해 말하고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="50b3d-129">**You are told about the threat**.</span></span> <span data-ttu-id="50b3d-130">조직에서 [끝점용 Microsoft Defender를](microsoft-defender-endpoint.md)사용하는 경우 보안 운영 팀도 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-130">(If your organization is using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), your security operations team is notified, too.)</span></span>

2. <span data-ttu-id="50b3d-131">**Microsoft Defender 바이러스 백신은 사용자(및** 조직의 보안 팀)가 장치에서 랜섬웨어를 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-131">**Microsoft Defender Antivirus helps you (and your organization's security team) remove the ransomware** from your device(s).</span></span> <span data-ttu-id="50b3d-132">(조직에서 끝점에 Microsoft Defender를 사용하는 경우 보안 운영 팀은 다른 장치가 감염된지 여부를 확인하여 적절한 조치를 취할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="50b3d-132">(If your organization is using Microsoft Defender for Endpoint, your security operations team can determine whether other devices are infected and take appropriate action, too.)</span></span>

3. <span data-ttu-id="50b3d-133">**OneDrive에서** 파일을 복구하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-133">**You get the option to recover your files in OneDrive**.</span></span> <span data-ttu-id="50b3d-134">OneDrive 파일 복원 기능을 사용하면 OneDrive의 파일을 랜섬웨어 공격이 발생하기 전의 상태로 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-134">With the OneDrive Files Restore feature, you can recover your files in OneDrive to the state they were in before the ransomware attack occurred.</span></span> <span data-ttu-id="50b3d-135">랜섬웨어 검색 및 [파일 복구를 참조하세요.](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)</span><span class="sxs-lookup"><span data-stu-id="50b3d-135">See [Ransomware detection and recovering your files](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f).</span></span>

<span data-ttu-id="50b3d-136">시간을 생각하면 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-136">Think of the time and hassle this can save.</span></span> 

## <a name="integration-means-better-protection"></a><span data-ttu-id="50b3d-137">통합은 더 나은 보호를 의미</span><span class="sxs-lookup"><span data-stu-id="50b3d-137">Integration means better protection</span></span>

<span data-ttu-id="50b3d-138">끝점용 Microsoft Defender와 통합된 Office 365용 Microsoft Defender는 조직에 대한 더 나은 보호를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-138">Microsoft Defender for Office 365 integrated with Microsoft Defender for Endpoint means better protection for your organization.</span></span> <span data-ttu-id="50b3d-139">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-139">Here's how:</span></span>

- <span data-ttu-id="50b3d-140">[Microsoft Defender for Office 365는 Office](/microsoft-365/security/office-365-security/office-365-atp) 문서의 전자 메일 메시지, 전자 메일 첨부 파일 및 링크(URL)에 있는 악의적인 위협에 대해 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-140">[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp) safeguards your organization against malicious threats posed in email messages, email attachments, and links (URLs) in Office documents.</span></span>

    <span data-ttu-id="50b3d-141">그리고</span><span class="sxs-lookup"><span data-stu-id="50b3d-141">AND</span></span>

- <span data-ttu-id="50b3d-142">[끝점용 Microsoft Defender는](microsoft-defender-endpoint.md) 사이버 위협으로부터 장치를 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하며, 보안 자세를 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-142">[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) protects your devices from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves your security posture.</span></span>

    <span data-ttu-id="50b3d-143">SO</span><span class="sxs-lookup"><span data-stu-id="50b3d-143">SO</span></span>

- <span data-ttu-id="50b3d-144">통합이 사용하도록 설정되면 보안 운영 팀은 Microsoft Defender 보안 센터()에서 검색된 URL 또는 전자 메일 메시지의 받는 사람이 사용하는 장치 목록과 해당 장치에 대한 최근 경고를 볼 수 있습니다. [https://securitycenter.windows.com](https://securitycenter.windows.com)</span><span class="sxs-lookup"><span data-stu-id="50b3d-144">Once integration is enabled, your security operations team can see a list of devices that are used by the recipients of any detected URLs or email messages, along with recent alerts for those devices, in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="50b3d-145">아직 수행하지 않은 경우 [Office 365용 Microsoft Defender를 끝점용 Microsoft Defender와 통합합니다.](/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)</span><span class="sxs-lookup"><span data-stu-id="50b3d-145">If you haven't already done so, [integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="more-good-reasons-to-use-onedrive"></a><span data-ttu-id="50b3d-146">OneDrive를 사용하는 더 좋은 이유</span><span class="sxs-lookup"><span data-stu-id="50b3d-146">More good reasons to use OneDrive</span></span>

<span data-ttu-id="50b3d-147">랜섬웨어로부터의 보호는 파일을 OneDrive에 저장하는 한 가지 좋은 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-147">Protection from ransomware is one great reason to put your files in OneDrive.</span></span> <span data-ttu-id="50b3d-148">또한 이 비디오에 요약된 몇 가지 좋은 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-148">And there are several more good reasons, summarized in this video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/70b4d256-46fb-481f-ad9b-921ef5fd7bed]

## <a name="want-to-learn-more-see-these-resources"></a><span data-ttu-id="50b3d-149">추가 정보가 필요하십니까?</span><span class="sxs-lookup"><span data-stu-id="50b3d-149">Want to learn more?</span></span> <span data-ttu-id="50b3d-150">다음 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="50b3d-150">See these resources:</span></span>

- [<span data-ttu-id="50b3d-151">OneDrive</span><span class="sxs-lookup"><span data-stu-id="50b3d-151">OneDrive</span></span>](/onedrive)

- [<span data-ttu-id="50b3d-152">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="50b3d-152">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

- [<span data-ttu-id="50b3d-153">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="50b3d-153">Microsoft Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)