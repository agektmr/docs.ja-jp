---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f107847ddd48805f4779ff94c4e436a176688030
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699026"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>ICLRDomainManager::SetPropertiesForDefaultAppDomain メソッド
既定のアプリケーション ドメインを初期化するために使用されるプロパティを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nProperties`  
 [in]エントリ数`pwszPropertyNames`と`pwszPropertyValues`します。  
  
 `pwszPropertyNames`  
 [in]プロパティ名、またはプロパティがない場合は null の配列。 現時点では、このメソッドによって認識される唯一のプロパティ名は、"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"です。  
  
 `pwszPropertyValues`  
 [in]プロパティの値、またはプロパティがない場合は null の配列。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。  
  
|HRESULT|説明|  
|-------------|-----------------|  
|S_OK|メソッドは正常に完了しました。|  
|HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` このメソッドによって認識されないプロパティ名が含まれています。|  
  
## <a name="remarks"></a>Remarks  
 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES"のプロパティの値は、条件付きのアセンブリのリスト<xref:System.Security.AllowPartiallyTrustedCallersAttribute>(APTCA) 属性を<xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType>フラグは、既定のアプリケーションで部分的に信頼された呼び出し元を表示するようにするのにはドメイン。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MetaHost.h  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ホスティング](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
