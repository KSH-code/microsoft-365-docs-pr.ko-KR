---
title: 사용자 사서함을 공유 사서함으로 변환
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '개인 사서함을 한 사람이 아닌 여러 사람이 액세스할 수 있는 공유 사서함으로 변환하는 방법을 학습합니다. '
ms.openlocfilehash: caf3935b1ffb36989b2884c6811111531a061098
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393970"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>사용자 사서함을 공유 사서함으로 변환

사용자의 사서함을 공유 사서함으로 변환하면 모든 기존 전자 메일 및 일정이 보존됩니다. 이제 한 사람이 아닌 여러 사람이 액세스할 수 있는 공유 사서함에 있습니다. 나중에 공유 사서함을 사용자(개인) 사서함으로 다시 변환할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

**다음은 알아야 할 몇 가지 중요한 사항입니다.**

- 변환할 사용자 사서함에는 공유 사서함으로 변환하기 전에 라이선스가 할당되어 있습니다. 그렇지 않으면 사서함을 변환하는 옵션이 표시됩니다. 라이선스를 제거한 경우 사서함을 변환할 수 있도록 라이선스를 다시 추가합니다. 사서함을 공유 사서함으로 변환한 후 사용자 계정에서 라이선스를 제거할 수 있습니다.

- 공유 사서함에는 라이선스가 할당되지 않은 경우 최대 50GB의 데이터를 사용할 수 있습니다. 이보다 많은 데이터를 저장하려면 라이선스를 할당해야 합니다. 라이선스를 제거할 수 있도록 공유 사서함에서 대용량 전자 메일(예: 첨부 파일이 있는 전자 메일)을 삭제하여 축소해야 할 수 있습니다.

- 이전 사용자의 계정을 삭제하지 않습니다. 공유 사서함의 기준이 앵커되는 데 필요합니다. 사용자 계정을 이미 삭제한 경우 삭제된 사용자의 [사서함 변환을 참조하세요.](#convert-the-mailbox-of-a-deleted-user)

- 이 규칙은 사서함이 공유 사서함으로 변환된 후 그대로 유지됩니다.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Exchange 관리 센터를 사용하여 사서함 변환
 
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.

2. 받는 **사람 사서함** \> **을 선택합니다.**

3. 사용자 사서함을 선택합니다. 공유 **사서함으로 변환에서** 변환을 **선택합니다.**

4. 사서함이 50GB보다 작은 경우 사용자 에서 [](../manage/remove-licenses-from-users.md)라이선스를 제거하고 비용 지불을 중지할 수 있습니다. 사용자 계정을 삭제하지 않습니다. 공유 사서함은 앵커로 필요합니다. 조직을 떠나는 직원의 사서함을 변환하는 경우 추가 단계를 수행하여 더 이상 로그인할 수 없는지 해야 합니다. 에서 [이전 직원 제거를 Microsoft 365.](../add-users/remove-former-employee.md)
    
> [!NOTE]
> 사서함 변환 중에 사용자 암호를 다시 설정할 필요는 없습니다. 그러나 암호를 다시 설정하지  않은 경우 사서함 변환이 완료된 후에도 원래 사용자 이름과 암호가 계속 작동됩니다.

공유 사서함에 대해 알아야 할 다른 모든 내용은 [공유](about-shared-mailboxes.md) 사서함 및 공유 사서함 만들기를 [참조합니다.](create-a-shared-mailbox.md)

> [!NOTE]
> 공유 사서함에는 별도의 라이선스가 필요하지 않습니다. 그러나 원본 위치 보관을 사용하도록 설정하거나 공유 사서함에 원본 위치 유지 또는 소송 보존을 적용하려는 경우 Exchange Online Archiving이 있는 Exchange Online 계획 1 또는 Exchange Online 계획 2 라이선스를 사서함에 할당해야 입니다.

## <a name="convert-the-mailbox-of-a-deleted-user"></a>삭제된 사용자의 사서함 변환

사용자 계정을 삭제하고 이제 이전 사서함을 공유 사서함으로 변환하려는 경우를 고려합니다. 다음 작업을 해야 합니다.

1. [사용자 계정을 복원합니다.](../add-users/restore-user.md)

2. 라이선스가 Microsoft 365 할당되어 있는지 확인

3. 사용자의 암호를 다시 설정하십시오.
    
4. 사서함을 다시 만들 때까지 20-30분 정도 기다립니다.
    
5. 이제 이 페이지의 지침에 따라 사서함을 공유 사서함으로 변환합니다.
    
6. 그런 다음 사용자 사서함에서 라이선스를 제거할 수 있습니다. 사용자의 이전 사서함을 삭제하지 않습니다. 공유 사서함은 앵커로 필요합니다.
    
7. 공유 사서함에 구성원을 추가합니다.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>공유 사서함을 사용자의 (개인) 사서함으로 다시 변환

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.
   
2. 받는 **사람 공유** \> **를 선택합니다.**

3. 공유 사서함을 선택합니다. 일반 **사서함으로 변환에서** 변환을 **선택합니다.**

4. 관리 센터로 돌아갈 수 있습니다. 사용자 **아래에서** 이전 공유 사서함과 연결된 사용자 계정을 선택하십시오. 계정에 라이선스를 할당하고 암호를 다시 설정하십시오.

   사서함을 설정하는 데 몇 분 정도 걸릴 수 있지만 그 후에 해당 계정을 사용하게 될 사람이 준비됩니다. 로그인하면 공유 사서함에 있는 데 사용된 전자 메일 및 일정 항목이 표시됩니다.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>하이브리드 환경에서 사용자의 사서함 변환

하이브리드 환경에서 사용자 사서함을 공유 사서함으로 변환하는 Exchange 자세한 내용은 다음을 참조하세요.

 - [Cmdlet - 프레미스 환경의 원격 공유 사서함을 만들거나 수정하는 Exchange 있습니다.](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [공유 사서함은 하이브리드 배포에서 디렉터리 동기화가 실행된 후 예기치 않게 Exchange 변환됩니다.](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> 조직 관리 또는 받는 사람 관리 역할 그룹의 구성원인 경우 Exchange 관리 셸을 사용하여 사용자 사서함을 공유 사서함을 사내 공유 사서함으로 변경할 수 있습니다. 예를 들면 `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`와 같습니다.

## <a name="related-content"></a>관련 콘텐츠

[공유 사서함 정보](about-shared-mailboxes.md)(문서)\
[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)\
[공유 사서함 구성](configure-a-shared-mailbox.md)(문서)\
[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)\
[공유 사서함 문제 해결](resolve-issues-with-shared-mailboxes.md)(문서)