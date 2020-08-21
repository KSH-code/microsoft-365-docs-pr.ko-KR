---
title: 가상 인증서 컬렉션 설정 - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 관리자는 Exchange Online에서 S/MIME 인증서의 유효성을 검사하는 데 사용할 가상 인증서 컬렉션을 만드는 방법을 학습할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16c6d38882a69feb46aa3e8fadccd6e005426304
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825140"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>S/MIME 유효성 검사를 위해 Exchange Online에서 가상 인증서 컬렉션 설정

관리자는 S/MIME 인증서의 유효성을 검사하는 데 사용할 가상 인증서 컬렉션을 Exchange Online에서 구성해야 합니다. 이 가상 인증서 컬렉션은 SST 파일 이름 확장명이 포함된 인증서 저장소로 설정되어 있습니다. SST 파일에는 S/MIME 인증서 유효성을 검사할 때 사용되는 모든 루트 및 중간 인증서가 포함됩니다.

## <a name="create-and-save-an-sst"></a>SST 만들기 및 저장

구성 및 구성에서 Export-Certificate cmdlet을 사용하여 신뢰할 수 있는 컴퓨터에서 **인증서를 내보낸** 다음 SST로 지정하여 Windows PowerShell 이 SST 인증서 저장소 _파일을_ 만들 수 있습니다. 관련 지침은 [Export-Certificate를 참조하세요.](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)

SST 인증서 저장소 파일을 한 번 지한 후에는 Exchange Online PowerShell에서 다음 구문을 사용하여 Exchange Online 가상 인증서 저장소에 SST 파일 콘텐츠를 저장합니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

이 예에서는 SST 파일 C:\My Documents\Exported Certificate Store.sst를 가져옵니다.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SmimeConfig를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>인증서가 유효한지 확인

Exchange Online에서는 인증서 유효성 검사에 SST만 사용됩니다.

## <a name="more-information"></a>추가 정보

[메시지 서명 및 암호화를 위한 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
