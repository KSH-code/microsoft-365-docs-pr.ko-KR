---
title: S/MIME 설정 구성 - 웹에서 Outlook의 경우 Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online에서 웹용 Outlook에서 S/MIME 설정을 보고 구성하기 위해 Exchange Online 관리자가 수행해야 하는 작업에 대한 간략한 설명입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825704"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>웹용 Outlook용 Exchange Online의 S/MIME 설정 구성

Exchange Online 관리자는 웹용 Outlook(이전의 Outlook Web App)을 설정하여 S/MIME으로 보호되는 메시지 보내기와 받기를 허용할 수 있습니다. **Get-SmimeConfig 및** **Set-SmimeConfig** cmdlet을 사용하여 Exchange Online PowerShell에서 이 기능을 보고 관리합니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

구문과 매개 변수에 대한 자세한 내용은 [Get-SmimeConfig 및](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) [Set-SmimeConfig를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>새로운 Microsoft Edge에 대한 고려 사항(Chromium 기반)

새로운 [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) 웹 브라우저에서 웹용 Outlook에서 S/MIME을 사용하려면 사용자(또는 다른 관리자)에서 Microsoft Edge 브라우저 확장명이 새 Microsoft Edge에 Microsoft S/MIME 확장명을 설치하도록 **ExtensionInstallForcelist라는** Microsoft Edge 브라우저 정책을 설정하고 구성해야 합니다. 정책 값은 다음과 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 같습니다. 또한 이 정책을 적용하려면 도메인 가입 또는 Azure AD 가입 디바이스가 필요하므로 새 Microsoft Edge 브라우저에서 S/MIME을 사용하려면 도메인 가입 또는 Azure AD 가입 장치가 필요합니다.

**ExtensionInstallForcelist 정책에 대한 자세한** 내용은 [ExtensionInstallForcelist를 참조하십시오.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

이 단계는 새 Microsoft Edge를 사용하기 위한 필수 조건입니다. 사용자가 설치한 S/MIME 컨트롤은 대체되지 않습니다. 사용자에게 S/MIME를 처음 사용하는 동안 Outlook에서 S/MIME 컨트롤을 다운로드하고 설치하라는 메시지가 표시됩니다. 또는 사용자는 자동으로 웹용 Outlook 설정에서 **S/MIME으로** 이동하여 컨트롤의 다운로드 링크를 가져올 수 있습니다.

## <a name="considerations-for-chrome"></a>Chrome에 대한 고려 사항

Google Chrome 웹 브라우저에서 웹용 Outlook에서 S/MIME을 사용하려면 사용자 또는 다른 관리자는 **ExtensionInstallForcelist라는** Chromium 정책을 설정하고 구성해야 Microsoft S/MIME 확장명이 Chrome에 설치됩니다. 정책 값은 다음과 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 같습니다. 또한 이 정책을 적용하려면 도메인에 가입된 컴퓨터가 필요하므로 Chrome에서 S/MIME을 효과적으로 사용하려면 도메인에 가입된 컴퓨터가 필요합니다.

**ExtensionInstallForcelist 정책에 대한 자세한** 내용은 [ExtensionInstallForcelist를 참조하십시오.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

이 단계는 Chrome 사용에 대한 필수 구성 요소입니다. 사용자가 설치한 S/MIME 컨트롤은 대체되지 않습니다. 사용자에게 S/MIME를 처음 사용하는 동안 Outlook에서 S/MIME 컨트롤을 다운로드하고 설치하라는 메시지가 표시됩니다. 또는 사용자는 자동으로 웹용 Outlook 설정에서 **S/MIME으로** 이동하여 컨트롤의 다운로드 링크를 가져올 수 있습니다.

## <a name="for-more-information"></a>자세한 내용

[메시지 서명 및 암호화를 위한 S/MIME](s-mime-for-message-signing-and-encryption.md)
