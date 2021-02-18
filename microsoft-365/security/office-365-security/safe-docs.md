---
title: Office 365용 Microsoft Defender의 안전 문서
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 또는 Microsoft 365 E5 보안의 안전한 문서에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288588"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="75c72-103">Microsoft 365 E5에서 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="75c72-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="75c72-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="75c72-104">**Applies to**</span></span>
- [<span data-ttu-id="75c72-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="75c72-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="75c72-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75c72-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="75c72-107">안전한 문서는 Microsoft 365 E5 또는 Microsoft 365 E5 Security의 기능으로, [끝점용 Microsoft Defender를](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 사용하여 보호된 보기에서 연 문서 및 파일을 검사합니다. [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="75c72-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="75c72-108">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="75c72-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="75c72-109">안전한 문서는 *Microsoft 365 E5 또는 Microsoft 365 E5* *보안* 라이선스가 있는 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="75c72-110">이러한 라이선스는 Office 365용 Microsoft Defender 요금제에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="75c72-111">안전한 문서는 엔터프라이즈용 Microsoft 365 앱(이전의 Office 365 ProPlus) 버전 2004 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="75c72-112"><https://protection.office.com>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="75c72-113">**ATP** 안전한 첨부 파일 페이지로 직접 이동하기 위해 를 을 을(를) 를 <https://protection.office.com/safeattachmentv2> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="75c72-114">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75c72-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="75c72-115">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-115">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="75c72-116">안전한 문서 설정을 구성하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="75c72-117">안전 문서 설정에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="75c72-118">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75c72-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="75c72-119">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="75c72-120">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75c72-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="75c72-121">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="75c72-122">Microsoft는 데이터를 어떻게 처리하나요?</span><span class="sxs-lookup"><span data-stu-id="75c72-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="75c72-123">보호를 유지하기 위해 안전한 문서는 분석을 위해 [Microsoft Defender for Endpoint 클라우드로](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 파일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="75c72-124">끝점용 Microsoft Defender가 데이터를 처리하는 방법에 대한 자세한 내용은 끝점 데이터 저장소 및 개인 정보 보호용 [Microsoft Defender에서](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="75c72-125">안전한 문서에서 보낸 파일은 분석에 필요한 시간(일반적으로 24시간 미만)이 지난 시간 동안 Defender에 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="75c72-126">보안 및 & 센터를 사용하여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="75c72-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="75c72-127">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP** 안전한 첨부 파일로 이동한 다음 전역 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75c72-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="75c72-128">전역 **설정이** 나타나면 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="75c72-129">**Office 클라이언트에** 대해 안전한 문서 켜기: 오른쪽으로 토글을 이동하여 기능을 ![ 켜기: ](../../media/scc-toggle-on.png) 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="75c72-130">**안전한 문서에서** 파일을 악의적인 것으로 식별한 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용: 이 옵션을 해제(토글을 왼쪽으로 유지: 토글 해제)하는 것이 좋습니다. ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="75c72-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="75c72-131">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-131">When you're finished, click **Save**.</span></span>

   ![안전 첨부 파일 페이지에서 전역 설정을 선택한 후의 안전한 문서 설정](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="75c72-133">Exchange Online PowerShell을 사용하여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="75c72-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="75c72-134">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="75c72-135">_EnableSafeDocs_ 매개 변수는 전체 조직에 대해 안전한 문서를 사용하도록 설정하거나 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="75c72-136">_AllowSafeDocsOpen_ 매개 변수는 문서가 악성으로 식별된 경우 사용자가 보호된 보기(즉, 문서를 여는 경우)를 허용하거나 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="75c72-137">이 예에서는 전체 조직에 대해 안전한 문서를 사용할 수 있도록 하여 사용자가 보호된 보기에서 악의적인 것으로 확인된 문서를 열지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="75c72-138">구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="75c72-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="75c72-139">작동 여부는 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="75c72-139">How do I know this worked?</span></span>

<span data-ttu-id="75c72-140">안전한 문서를 사용하도록 설정하고 구성해야 하는지 확인을 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="75c72-141">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP**   안전한 첨부 파일로 이동하고 전역 설정을 클릭한 다음 **Office** 클라이언트에 대해 안전한 문서 켜기 기능을 확인하고 안전한 문서가 파일을 악의적인 설정으로 식별하는 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="75c72-142">Exchange Online PowerShell에서 다음 명령을 실행하고 속성 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="75c72-143">다음 파일을 통해 안전한 문서 보호를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="75c72-144">이러한 문서는 맬웨어 방지 EICAR.TXT 바이러스 백신 솔루션을 테스트하기 위한 파일과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="75c72-145">파일이 해로운 것은 아니며 안전한 문서 보호를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="75c72-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="75c72-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="75c72-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="75c72-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="75c72-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="75c72-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="75c72-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
