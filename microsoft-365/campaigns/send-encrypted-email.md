---
title: 암호화된 전자 메일 보내기
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 암호화된 전자 메일을 사용하여 암호화된 전자 메일을 보내는 Outlook.
ms.openlocfilehash: 789477557801f2c8b89fa2bb281d0b0f2faf993a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186444"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>중요한 전자 메일을 암호화하거나 레이블을 지정합니다.

데이터 및 캠페인 정보는 중요하고 종종 기밀입니다. 암호화 및 민감도 레이블을 사용하여 이 중요한 정보를 보호할 수 있으므로 사용자와 전자 메일 받는 사람이 정보를 필요한 민감도로 처리합니다.

## <a name="best-practices"></a>모범 사례

기밀 또는 중요한 정보가 있는 전자 메일을 보내기 전에 다음을 켜는 것이 있습니다.

- **암호화:** 전자 메일을 암호화하여 전자 메일의 정보 개인 정보를 보호할 수 있습니다. 전자 메일 메시지를 암호화하면 읽을 수 있는 일반 텍스트에서 스크램블된 사이퍼 텍스트로 변환됩니다. 메시지를 암호화하는 데 사용되는 공개 키와 일치하는 개인 키가 있는 받는 사람만 메시지를 읽을 수 있습니다. 그러나 해당 개인 키가 없는 받는 사람에게는 배달할 수 없는 텍스트가 표시됩니다. 관리자는 특정 기준을 충족하는 메시지를 자동으로 암호화하는 규칙을 정의할 수 있습니다. 예를 들어 관리자는 조직 외부로 전송된 모든 메시지 또는 특정 단어나 구를 언급하는 모든 메시지를 암호화하는 규칙을 만들 수 있습니다. 암호화 규칙은 자동으로 적용됩니다.
- **민감도 레이블:** 또한 캠페인은 파일 및 전자 메일에 적용할 수 있는 민감도 레이블을 설정하여 캠페인의 정보 보호 정책을 준수하도록 할 수 있습니다. 레이블을 설정하면 레이블이 전송된 경우에도(예: 메시지에 헤더로 표시) 전자 메일과 함께 레이블이 지속됩니다.

![레이블 및 암호화에 대한 설명이 있는 전자 메일 다이어그램입니다.](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>설정하기

미리 정의된 규칙을 충족하지 않는 메시지를 암호화하거나 관리자가 규칙을 설정하지 않은 경우 메시지를 보내기 전에 다양한 암호화 규칙을 적용할 수 있습니다. Outlook 2013 또는 2016에서 암호화된 메시지를 보내거나 Mac용 Outlook 2016 사용 > 옵션을 선택한 다음 필요한 보호 옵션을 선택합니다. 또한 암호화된 메시지의 보호 단추를  선택하여 암호화된 메시지를 웹용 Outlook. 자세한 내용은 PC용 에서 암호화된 메시지 보내기, Outlook [회신을 참조하세요.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="admin-settings"></a>관리자 설정

전자 메일 암호화 설정에 대한 자세한 내용은 에서 전자 메일 [암호화를 Microsoft 365.](../compliance/email-encryption.md)

### <a name="automatically-encrypt-email-messages"></a>전자 메일 메시지 자동 암호화

관리자는 메일 흐름 규칙을 만들어 캠페인에서 보내고 받은 전자 메일 메시지를 자동으로 보호할 수 있습니다. 발신 전자 메일 메시지를 암호화하고 조직 내부에서 전송된 암호화된 메시지 또는 조직에서 보낸 암호화된 메시지에 대한 답장에서 암호화를 제거하는 규칙을 설정합니다.

메일 흐름 규칙을 만들어 새 OME(Office 365 메시지 암호화) 기능을 사용하여 전자 메일 메시지를 암호화합니다. EAC(Exchange 관리 센터)를 사용하여 새 OME 기능으로 메시지 암호화를 트리거하기 위한 메일 흐름 규칙을 정의합니다. 

1. 웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 로그인합니다.
2. 관리 타일을 선택하세요.
3. In the admin center, choose **Admin centers > Exchange.**

자세한 내용은 [Define mail flow rules to encrypt email messages를 참조하세요.](../compliance/define-mail-flow-rules-to-encrypt-email.md)

### <a name="brand-your-encryption-messages"></a>암호화 메시지 브랜드

캠페인 브랜다를 적용하여 전자 메일 메시지의 모양과 텍스트를 사용자 지정할 수도 있습니다. 자세한 내용은 암호화된 메시지에 조직의 브랜드 [추가를 참조하세요.](../compliance/email-encryption.md)