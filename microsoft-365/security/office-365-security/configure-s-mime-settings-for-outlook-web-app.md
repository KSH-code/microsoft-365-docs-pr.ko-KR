---
title: 웹용 Outlook에 대 한 Exchange Online의 S/MIME 설정 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online 관리자가 웹에서 Outlook의 S/MIME 설정을 보고 구성 하기 위해 수행 해야 하는 작업에 대 한 간략 한 설명입니다.
ms.openlocfilehash: 354b247c2b0e0e610e6cb0626f4a404b582db717
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960324"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>웹용 Outlook에 대 한 Exchange Online의 S/MIME 설정 구성

Exchange Online 관리자는 웹에서 Outlook (이전의 Outlook Web App)을 설정 하 여 S/MIME로 보호 된 메시지를 보내고 받을 수 있습니다. **Get-smimeconfig** 및 **get-smimeconfig** cmdlet을 사용 하 여 Exchange Online PowerShell에서이 기능을 보고 관리 합니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.

구문과 매개 변수에 대 한 자세한 내용은 [get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) 및 [get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)를 참조 하십시오.

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>새 Microsoft Edge에 대 한 고려 사항 (Chromium 기반)

새 [Microsoft edge](https://www.microsoft.com/windows/microsoft-edge) 웹 브라우저에서 웹의 Outlook에서 S/mime을 사용 하려면 사용자 (또는 다른 관리자)가 새 microsoft Edge에 microsoft S/MIME 확장명을 설치 하도록 **Extensioninstallforcelist** 라는 microsoft edge 브라우저 정책을 설정 하 고 구성 해야 합니다. 정책 값은 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`입니다. 또한이 정책을 적용 하려면 도메인에 가입 된 컴퓨터가 필요 하므로 새 Microsoft Edge 브라우저에서 S/MIME을 사용 하려면 도메인에 가입한 컴퓨터가 필요 합니다.

**Extensioninstallforcelist** 정책에 대 한 자세한 내용은 [extensioninstallforcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)를 참조 하십시오.

이 단계는 새 Microsoft Edge를 사용 하기 위한 필수 구성 요소입니다. 사용자가 설치한 S/MIME 컨트롤은 대체 되지 않습니다. S/MIME을 처음 사용할 때 Outlook에서 S/MIME 컨트롤을 다운로드 하 고 설치 하 라는 메시지가 사용자에 게 표시 됩니다. 또는 사용자가 웹 설정에 따라 Outlook에서 **S/MIME** 로 바로 이동 하 여 컨트롤의 다운로드 링크를 받을 수 있습니다.

## <a name="considerations-for-chrome"></a>Chrome에 대 한 고려 사항

Google Chrome 웹 브라우저에서 웹의 Outlook에서 S/MIME을 사용 하려면 사용자 (또는 다른 관리자)가 Chromium 정책을 **설정 하 고** 구성 해야 합니다. 정책 값은 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`입니다. 또한이 정책을 적용 하려면 도메인에 가입 된 컴퓨터가 필요 하므로 Chrome에서 S/MIME을 사용 하려면 도메인에 가입 된 컴퓨터가 필요 합니다.

**Extensioninstallforcelist** 정책에 대 한 자세한 내용은 [extensioninstallforcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)를 참조 하십시오.

이 단계는 Chrome을 사용 하기 위한 필수 구성 요소입니다. 사용자가 설치한 S/MIME 컨트롤은 대체 되지 않습니다. S/MIME을 처음 사용할 때 Outlook에서 S/MIME 컨트롤을 다운로드 하 고 설치 하 라는 메시지가 사용자에 게 표시 됩니다. 또는 사용자가 웹 설정에 따라 Outlook에서 **S/MIME** 로 바로 이동 하 여 컨트롤의 다운로드 링크를 받을 수 있습니다.

## <a name="for-more-information"></a>자세한 내용

[메시지 서명 및 암호화를 위한 S/MIME](s-mime-for-message-signing-and-encryption.md)
