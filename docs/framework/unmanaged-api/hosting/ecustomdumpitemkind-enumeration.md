---
title: ECustomDumpItemKind 列挙型
ms.date: 03/30/2017
api_name:
- ECustomDumpItemKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpItemKind
helpviewer_keywords:
- ECustomDumpItemKind enumeration [.NET Framework hosting]
ms.assetid: 7105a6c8-6e4e-48de-ac3d-74ac75e5de2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e44f84ed92f90a51ac1c5c7327d6de7b89887c7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536517"
---
# <a name="ecustomdumpitemkind-enumeration"></a>ECustomDumpItemKind 列挙型
将来の拡張機能用に予約されて、 [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)構造体。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum {  
    DUMP_ITEM_None = 0  
} ECustomDumpItemKind;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`DUMP_ITEM_None`|将来使用するために予約されています。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICLRErrorReportingManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [ホスティングの列挙型](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
