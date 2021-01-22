---
title: 공유 사서함 만들기
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 공유 사서함을 만들어 회사의 여러 사용자가 하나의 주소로 전송된 전자 메일을 읽고 답장하는 업무를 나눌 수 있습니다.
ms.openlocfilehash: d0bd5770f347766638af0f0e66b9f961b3721697
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926597"
---
# <a name="create-a-shared-mailbox"></a>공유 사서함 만들기 

> [!NOTE]
> 조직에서 하이브리드 Exchange 환경을 사용하는 경우 온-프레미스 EAC(Exchange 관리 센터)를 사용하여 공유 사서함을 만들고 관리해야 합니다. [Exchange 관리 센터에서 공유 사서함을 만드는 방법](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019&preserve-view=true.)을 참조하세요.<br><br>
> 공유 사서함 또는 Outlook용 Microsoft 365 그룹 중 무엇을 만들어야 하는지 확실하지 않은 경우 [Compare groups](../create-groups/compare-groups.md)(그룹 비교)에서 지침을 확인하세요. 현재 공유 사서함은 Microsoft 365 그룹으로 마이그레이션할 수 없습니다. 이것이 원하는 것이라면 [여기에서 투표](https://go.microsoft.com/fwlink/?linkid=871518)를 통해 알려주세요.

사용자 그룹이 info@contoso.com과 같은 공통 전자 메일 주소에서 전자 메일을 모니터링하고 보낼 수 있도록 공유 사서함을 만들 수 있습니다. 그룹에 속한 사용자가 공유 사서함에 전송된 메시지에 회신하면 해당 전자 메일은 개별 사용자가 아닌 공유 사서함에서 발송된 것으로 나타납니다.

공유 사서함에는 공유 일정이 포함됩니다. 여러 중소기업에서는 모든 직원이 약속을 입력할 수 있는 공유 일정을 즐겨 사용합니다. 예를 들어 고객을 방문하는 직원이 세 명 있는 경우 세 명 모두 공유 일정을 사용하여 약속을 입력할 수 있습니다. 이렇게 하면 누가 어디에 있는지 모두에게 쉽게 알릴 수 있습니다.

공유 사서함을 만들기 전에 자세한 내용은 [공유 사서함 정보](about-shared-mailboxes.md)를 참조하세요.

## <a name="create-a-shared-mailbox-and-add-members"></a>공유 사서함 만들기 및 구성원 추가
  
1. 전역 관리자 계정 또는 Exchange 관리자 계정을 사용하여 로그인합니다. “**이 페이지에 액세스하거나 이 작업을 수행할 권한이 없습니다**”메시지가 나타나는 경우 관리자가 아닙니다. 

::: moniker range="o365-worldwide"

2. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

2. [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=848041)에서 **그룹** \> **공유 사서함** 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

2. [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=850627)에서 **그룹** \> **공유 사서함** 페이지로 이동합니다.

::: moniker-end
    
3. **공유 사서함** 페이지에서 **+ 사서함 추가** 를 선택합니다. 공유 사서함의 이름을 입력합니다. 마법사에서 이름이 선택되지만, 원하는 경우 편집할 수 있습니다.
    
    ![공유 사서함 이름을 지정합니다.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. **추가** 를 선택합니다. 몇 분 정도 기다린 다음에 구성원을 추가할 수 있습니다.

5. **다음 단계** 에서 **이 사서함에 구성원 추가** 를 선택합니다. 구성원은 이 공유 사서함으로 받는 메일과 보내는 회신을 볼 수 있습니다.

   ![구성원 추가를 선택합니다.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. **+구성원 추가** 단추를 선택합니다. 이 공유 사서함을 사용할 사람 옆에 확인 표시를 하고 **저장** 을 클릭합니다.

   ![공유 사서함에 구성원을 할당합니다.](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. **닫기** 를 선택합니다.

공유 일정이 포함된 공유 사서함을 만들었습니다. 이제 다음 단계인 공유 사서함 계정에 대한 로그인 차단으로 넘어갑니다.

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>공유 사서함 계정에 대한 로그인 차단

모든 공유 사서함에는 해당하는 사용자 계정이 있습니다. 공유 사서함을 만들 때 암호를 입력하라는 메시지가 표시되지 않으면 어떻게 하나요? 계정에 암호가 있지만 시스템이 생성(알 수 없음)한 것입니다. 계정을 사용하여 공유 사서함에 로그인해서는 안 됩니다.

그러나 관리자가 단순히 공유 사서함 사용자 계정의 암호를 재설정하면 어떻게 되나요? 또는 공격자가 공유 사서함 계정 자격 증명에 대한 액세스 권한을 얻으면 어떻게 되나요? 이런 경우 사용자 계정이 공유 사서함에 로그인하여 전자 메일을 보낼 수 있습니다. 이를 방지하려면 공유 사서함에 연결된 계정에 대한 로그인을 차단해야 합니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 사용자 계정 목록에서 공유 사서함의 계정을 찾습니다(예: 필터를 **라이선스가 없는 사용자** 로 변경).

3. 사용자를 선택하여 속성 창을 연 다음 **이 사용자 차단** 아이콘 및 ![이 사용자 차단 아이콘의 스크린 샷](../../media/block-user-icon.png)을 선택합니다.

   **참고**: 계정이 이미 차단된 경우 상단에 **로그인 차단됨** 이 표시되고 아이콘은 **이 사용자 차단 해제** 로 표시됩니다.

4. **이 사용자를 차단할까요?** 창에서 **사용자의 로그인 차단** 을 선택한 다음 **변경 사항 저장** 을 선택합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 사용자 계정 목록에서 공유 사서함의 계정을 찾은 다음(예: 보기를 **라이선스가 없는 사용자** 로 변경) 계정을 선택합니다.

3. 속성 플라이 아웃에서 **로그인 차단** 을 선택합니다.

    **참고:** 계정이 이미 차단된 경우 단추에 **로그인 차단 해제** 가 표시됩니다.

4. **로그인 상태 편집** 플라이 아웃에서 사용자의 로그인 차단이 선택되어 있는지 확인한 후 **저장** 을 선택한 다음 **닫기** 를 선택합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 사용자 계정 목록에서 공유 사서함의 계정을 찾은 다음(예: 보기를 **라이선스가 없는 사용자** 로 변경) 계정을 선택합니다.

3. 속성 플라이 아웃에서 **로그인 차단** 을 선택합니다.

    **참고:** 계정이 이미 차단된 경우 단추에 **로그인 차단 해제** 가 표시됩니다.

4. **로그인 상태 편집** 플라이 아웃에서 사용자의 로그인 차단이 선택되어 있는지 확인한 후 **저장** 을 선택한 다음 **닫기** 를 선택합니다.
::: moniker-end

Azure AD PowerShell을 사용하여 계정에 대한 로그인을 차단하는 방법(동시에 여러 계정 포함)에 대한 자세한 내용은 [Office 365 PowerShell을 사용하여 사용자 계정 차단](https://docs.microsoft.com/microsoft-365/enterprise/block-user-accounts-with-microsoft-365-powershell)을 참조하세요.

## <a name="add-the-shared-mailbox-to-outlook"></a>공유 사서함을 Outlook에 추가

회사에서 automapping을 활성화한 경우(대부분의 사용자가 기본값으로 활성화함) Outlook을 종료하고 다시 시작하면 사용자의 Outlook 앱에 공유 사서함이 자동으로 나타납니다. 

Automapping은 공유 사서함이 아니라 사용자의 사서함에서 설정됩니다.   즉 보안 그룹을 사용하여 공유 사서함에 액세스할 수 있는 사용자를 관리하려는 경우 automapping이 작동하지 않습니다. 따라서 automapping을 사용하려면 사용 권한을 명시적으로 할당해야 합니다. Automapping은 기본적으로 설정됩니다. 이 기능을 해제하는 방법은 [공유 사서함에 대한 automapping 제거](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)를 참조하세요.

Outlook의 공유 사서함에 대한 자세한 내용은 다음을 참조하세요.

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Outlook에서 공유 사서함 열기 및 사용</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">웹용 Outlook에 공유 사서함 추가</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook 모바일에 공유 사서함 추가</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Mac 용 Outlook에서 공유 폴더 또는 사서함 열기</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">공유 사서함에 규칙 추가</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>모바일 장치(휴대폰 또는 태블릿)에서 공유 사서함 사용

다음 두 가지 방법으로 모바일 장치의 공유 사서함에 액세스할 수 있습니다.
- <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">iOS용 Outlook 앱</a> 또는 <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Android 모바일용 Outlook 앱</a>에서 공유 사서함을 추가합니다. 
    
    자세한 내용은 <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook 모바일에 공유 사서함 추가</a>를 참조하세요.

- 브라우저를 열고 로그인한 다음 웹용 Outlook으로 이동합니다. 웹용 Outlook에서 공유 사서함에 액세스할 수 있습니다.

    자세한 내용은 <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">웹용 Outlook에 공유 사서함 추가</a>를 참조하세요.
    
> [!NOTE]
> 공유 사서함은 Outlook for iOS 앱 또는 Outlook for Android 모바일 앱에만 추가할 수 있습니다.

## <a name="use-the-shared-calendar"></a>공유 일정 사용

공유 사서함을 만들면 공유 일정이 자동으로 생성됩니다. 약속과 사람들이 있는 장소를 계속 확인하기 위해 SharePoint 일정보다는 공유 사서함 일정을 선호합니다. 공유 일정은 Outlook과 통합되어 있으며 SharePoint 일정보다 더 쉽게 사용할 수 있습니다.

1. Outlook 앱에서 일정 보기로 이동하고 공유 사서함을 선택합니다. 

2. 약속을 입력하면 공유 사서함의 구성원 모두가 약속을 볼 수 있습니다. 

3. 공유 사서함의 모든 구성원은 개인 약속과 마찬가지로 일정에 대한 약속을 만들고보고 관리할 수 있습니다. 공유 사서함의 구성원인 모든 사용자는 공유 일정에 따른 변경 내용을 볼 수 있습니다.

## <a name="related-articles"></a>관련 문서

[공유 사서함 정보](about-shared-mailboxes.md)

[공유 사서함 구성](configure-a-shared-mailbox.md)

[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)

[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)

[공유 사서함의 문제 해결](resolve-issues-with-shared-mailboxes.md)





