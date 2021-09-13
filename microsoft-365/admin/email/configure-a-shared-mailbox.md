---
title: 공유 사서함 설정 구성
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함을 만들고 전자 메일 전달 및 자동 응답과 같은 사용자에 대한 일부 설정을 구성합니다.
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184763"
---
# <a name="configure-shared-mailbox-settings"></a>공유 사서함 설정 구성

공유 [사서함을](create-a-shared-mailbox.md)만든 후 전자 메일 전달 및 자동 응답과 같은 사서함 사용자에 대한 일부 설정을 구성할 수 있습니다. 나중에 사서함 이름, 구성원 또는 구성원 권한과 같은 다른 설정을 변경할 수 있습니다. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>공유 사서함의 이름 또는 전자 메일 별칭을 변경하거나 기본 전자 메일 주소 변경

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음  이름, 전자 메일, 전자 메일 별칭 옆에 있는 **편집을 선택합니다.**

3. 새 이름을 입력하거나 다른 별칭을 추가합니다. 기본 전자 메일 주소를 변경하려면 사서함에 전자 메일 별칭이 두 개 이상 있어야 합니다.

4. **저장** 을 선택합니다.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>공유 사서함으로 전송되는 전자 메일 전달

공유 사서함으로 전송된 전자 메일을 전달하기 위해 공유 사서함에 라이선스를 할당할 필요는 없습니다. 메시지를 유효한 전자 메일 주소 또는 메일로 전달할 수 있습니다.

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음 전자 메일 전달 **편집 을** \> **선택합니다.**
    
3. 토글을 **으로 설정하고** 메시지를 전달할 전자 메일 주소를 하나 입력합니다. 유효한 전자 메일 주소일 수 있습니다. 여러 주소로 전달하려면 주소에 대한 메일 그룹을 만든 다음 이 상자에 그룹의 이름을 입력해야 합니다. [](/office365/admin/setup/create-distribution-lists)
    
4. **저장** 을 선택합니다.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>공유 사서함에서 자동 회신 보내기

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음 자동 답장 편집 **을** \> **선택합니다.**
    
3. 토글을 **으로 설정하고** 조직 내부 또는 조직 외부의 사용자에 대한 회신을 보낼지 여부를 선택하십시오.

4. 조직 내부 및 사용자에게 보내려는 회신을 입력합니다. 이미지는 추가할 수 없으며 텍스트만 추가할 수 있습니다.

5. 조직 *외부의* 사용자들에게도 회신을 보내고 싶은 경우, 확인란을 선택하고 회신을 받을 대상을 선택하고 텍스트를 입력합니다. 조직 외부 사용자에게만 보내는 방법은 없지만, 조직 내부 사용자에게만 보낼 수는 있습니다.

6. **저장** 을 선택합니다.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>모든 사람이 보낸 전자 메일(회신)을 볼 수 있도록 허용

기본적으로 공유 사서함에서 보낸 메시지는 공유 사서함의 보낸 편지함 폴더에 저장되지 않습니다. 대신, 메시지를 보낸 사람의 보낸 편지함 폴더에 저장됩니다.

모든 사용자가 보낸 전자 메일을 볼 수 있도록 허용하려면 관리 센터에서 공유 사서함 설정을 편집하고 보낸 항목 **편집 을** \> **선택합니다.**


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>공유 사서함이 Microsoft 전자 메일에 액세스하는 데 사용할 수 있는 앱 선택

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음 전자 메일 앱 편집 **을** \> **선택합니다.**

3. 구성원이 공유 사서함에 액세스하는 데 사용할 수 있도록 할 모든 앱에 대해 토글을 으로 설정하십시오.  사용하지 않는 모든  앱에 대해 토글을 끄기로 설정하세요. 

4. **저장** 을 선택합니다.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>공유 사서함에 소송 보류

소송 보유에 대한 자세한 내용은 [Create a Litigation Hold를 참조합니다.](../../compliance/create-a-litigation-hold.md)

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음 소송 보류 편집 **을** \> **선택합니다.**

3. 토글을 **으로 설정** 

4. 선택적으로 기간, s 보류에 대한 메모 및 추가 정보가 있는 URL을 입력합니다.  

5. **저장** 을 선택합니다.


## <a name="add-or-remove-members"></a>구성원 추가 또는 제거

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음 구성원 편집 **을** \> **선택합니다.**

3. 다음 중 하나를 수행합니다.
   - 구성원을 추가하려면 구성원 **추가를** 선택하고 추가할 구성원을 검색하거나 선택한 다음 저장을 **선택합니다.**
   - 구성원을 제거하려면 검색 상자를 사용하여 필요한 경우 구성원을 검색하고 구성원 이름 **옆의 X를** 선택한 다음 저장을 **선택합니다.** 

4. 저장을 **다시** 선택합니다.

## <a name="add-or-remove-permissions-of-members"></a>구성원의 사용 권한 추가 또는 제거

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음 구성원 **권한** 사용자 \> **지정 을 선택합니다.**

3. **구성원에** 대해 변경할 권한 옆의 편집을 선택합니다. 

4. 다음 중 하나를 수행합니다.
   - 추가 구성원에게 해당 권한을 부여하려면 사용 권한 **추가를** 선택하고 추가할 구성원을 검색하거나 선택한 다음 저장을 **선택합니다.**
   - 구성원에서 사용 권한을 제거하려면 필요한 경우 검색 상자를 사용하여 구성원을 검색하고 구성원 이름 옆의 **X를** 선택한 다음 저장을 **선택합니다.** 

4. 저장을 **다시** 선택합니다.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>전체 주소 목록에서 공유 사서함 표시 또는 숨기기

전체 주소 목록에 공유 사서함을 표시하지 않는 경우 사서함은 조직의 주소 목록에 나타나지 않지만 해당 사서함으로 전송된 전자 메일을 계속 받게 됩니다. 

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.

2. 편집할 공유 사서함을 선택한 다음 전체 주소 목록 편집에서 **표시를** \> **선택합니다.**

3. 토글을 설정 **또는 해제로** **설정** 

4. **저장** 을 선택합니다.

> [!NOTE]
> 주소 목록에서 공유 사서함을 숨기면 새 공유 사서함 구성원이 주소 목록에 공유 사서함이 다시 표시될 때까지 Outlook 프로필에 숨겨진 사서함을 추가할 수 없습니다. 

## <a name="related-content"></a>관련 콘텐츠

[공유 사서함 정보](about-shared-mailboxes.md)(문서)\
[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)\
[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)(문서)\
[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)\
[공유 사서함 문제 해결](resolve-issues-with-shared-mailboxes.md)(문서)