---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 643bfd9f17474241a9291734eb52910f97f9ad2d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495644"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a>ICorDebugThread4::GetCurrentCustomDebuggerNotification メソッド
現在の取得[icordebugmanagedcallback 3::customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)現在のスレッド上のオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetCurrentCustomDebuggerNotification(  
    [out] ICorDebugValue **ppNotificationObject  
    );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppNOtificationObject`  
 [out]現在へのポインター`ICorDebugManagedCallback3::CustomNotification`現在のスレッド上のオブジェクト。  
  
## <a name="remarks"></a>Remarks  
 値`ppNotificationObject`内からメソッドを呼び出さない場合は null を`ICorDebugManagedCallback3::CustomNotification`コールバック、または現在の通知オブジェクトが存在しない場合。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorDebugThread4 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
