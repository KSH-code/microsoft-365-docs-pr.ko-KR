---
title: Exchange의 보존에 대해 자세히 알아보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Exchange에서 보존의 작동 방식을 알아봅니다.
ms.openlocfilehash: e12f46b68feb4b64ade14cfb046061d89e1a607c
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394715"
---
# <a name="learn-about-retention-for-exchange"></a>Exchange의 보존에 대해 자세히 알아보기

Exchange에 관한 정보를 담고 있으므로 이 문서의 정보는 [보존 정책에 대해 자세히 알아보기](retention.md)를 보완합니다.

## <a name="how-retention-works-for-exchange"></a>Exchange에서 보존의 작동 방식

사서함 및 공용 폴더 모두 항목을 보존하기 위해 [복구 가능한 항목 폴더](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)를 사용합니다. eDiscovery 권한을 할당 받은 사용자만 다른 사용자의 복구 가능한 항목 폴더에서 항목을 볼 수 있습니다.
  
사용자가 지운 편지함 폴더 이외의 폴더에서 메시지를 삭제하면 기본적으로 해당 메시지는 지운 편지함 폴더로 이동됩니다. 사용자가 지운 편지함 폴더에서 항목을 삭제하면 해당 메시지는 복구할 수 있는 항목 폴더로 이동합니다. 그러나 사용자는 모든 폴더에서 Shift+Delete로 항목을 일시적으로 삭제할 수 있습니다. 이 경우 항목이 지운 편지함 폴더를 무시하고 복구할 수 있는 항목 폴더로 바로 이동합니다.
  
보존 설정을 Exchange 데이터에 적용하면 타이머 작업이 복구 가능한 항목 폴더의 항목을 주기적으로 평가합니다. 항목이 하나 이상의 보존 정책이나 보존 레이블의 규칙과 일치하지 않는 경우, 항목은 복구 가능한 항목 폴더에서 영구적으로 삭제됩니다(영구 삭제).

타이머 작업은 최대 7일이 걸릴 수 있으며 Exchange 위치에는 적어도 10MB가 포함되어 있어야 합니다.
  
사용자가 메시지의 제목, 본문, 첨부 파일, 보내는 사람 및 받는 사람, 보낸 날짜 또는 받은 날짜와 같은 사서함 항목의 속성을 변경하려고 하면 변경이 적용되기 전에 원본 항목의 복사본이 복구 가능한 항목 폴더에 저장됩니다. 이 작업은 후속 변경이 있을 때마다 진행됩니다. 보존 기간이 끝나면 복구 가능한 항목 폴더의 복사본이 영구적으로 삭제됩니다.

보존 설정을 Exchange 콘텐츠에 적용한 후에 콘텐츠가 사용하는 경로는 보존 설정이 보존 후 삭제하는지, 아니면 보존 또는 삭제 한 가지만 실행하는지 여부에 따라 달라집니다.

보존 설정이 보존 및 삭제인 경우:

![전자 메일과 공용 폴더의 보존 흐름 다이어그램](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. 사용자가 보존 기간 내에 **항목을 수정하거나 영구적으로 삭제하면**(SHIFT+DELETE를 사용하거나 삭제된 항목에서 삭제하는 경우) 항목이 복구 가능한 항목 폴더로 이동(또는 편집한 경우 복사)됩니다. 여기에서 타이머 작업이 주기적으로 실행되며 보존 기간이 만료된 항목을 식별합니다. 식별된 항목은 보존 기간 종료일로부터 14일 이내에 영구적으로 삭제됩니다. 14일은 기본값이며, 최대 30일로 설정할 수 있습니다.

2. 보존 기간 내에 **항목이 수정되거나 삭제되지 않으면** 사서함의 모든 폴더에서 동일한 프로세스가 주기적으로 실행되며 보존 기간이 만료된 항목을 식별합니다. 식별된 항목은 보존 기간 종료일로부터 14일 이내에 영구적으로 삭제됩니다. 14일은 기본값이며, 최대 30일로 설정할 수 있습니다. 

보존 설정이 보존 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보존 및 삭제의 변형입니다.

### <a name="content-paths-for-retain-only-retention-settings"></a>보존 전용 보존 설정의 컨텐츠 경로

1. 보존 기간 동안 **항목이 수정되거나 삭제된 경우**: 복구 가능한 항목 폴더의 사본이 항목이 만료된 후 14일 이내에 영구적으로 삭제되면 원래 항목의 사본이 복구 가능한 항목 폴더에 작성되고 보존 기간이 끝날 때까지 보존됩니다. 

2. 보존 기간 동안 **항목이 수정되거나 삭제되지 않은 경우**: 보존 기간 전후에는 아무 것도 발생하지 않습니다. 항목은 원래 위치에 남아 있습니다.

### <a name="content-paths-for-delete-only-retention-settings"></a>삭제 전용 보존 설정의 컨텐츠 경로

1. 구성된 기간에 **항목이 삭제되지 않은 경우**: 보존 정책에서 구성된 기간이 끝나면 항목은 복구 가능한 항목 폴더로 이동됩니다. 

2. 구성된 기간에 **항목이 삭제된 경우**: 항목은 즉시 복구 가능한 항목 폴더로 이동합니다. 사용자가 해당 항목을 삭제하거나 복구 가능한 항목 폴더를 비우면 항목이 영구적으로 삭제됩니다. 그렇지 않으면 14일 동안 복구 가능한 항목 폴더에있는 항목이 영구적으로 삭제됩니다. 

## <a name="when-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우 

조직에서 나간 사용자의 사서함이 보존 정책에 포함되어 있는 경우, 사용자의 Microsoft 365 계정이 삭제되면 해당 사서함이 비활성화됩니다. 비활성화된 사서함의 콘텐츠 또한 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다. 자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.

## <a name="configuration-guidance"></a>구성 지침

Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.

Exchange의 보존 정책 또는 보존 레이블을 구성할 준비가 되면 다음 지침을 참조하세요.
- [보존 정책 만들기 및 구성하기](create-retention-policies.md)
- [보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)
- [보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)