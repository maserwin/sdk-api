---
UID: NF:powersetting.PowerSetUserConfiguredACPowerMode
title: PowerSetUserConfiguredACPowerMode function (powersetting.h)
description: Sets the user configured power mode to use when the device is on AC.
helpviewer_keywords: ["GUID_PROCESSOR_SETTINGS_SUBGROUP","NO_SUBGROUP_GUID","PowerSetUserConfiguredACPowerMode","PowerSetUserConfiguredACPowerMode function","base.powersetuserconfiguredacpowermode","powersetting/PowerSetUserConfiguredACPowerMode","powrprof/PowerSetUserConfiguredACPowerMode"]
old-location:
tech.root: power
ms.assetid: 8b1f8edb-d30b-447f-9277-5cc9b9aa4976
ms.date: 07/24/2023
ms.keywords: GUID_PROCESSOR_SETTINGS_SUBGROUP, NO_SUBGROUP_GUID, PowerSetUserConfiguredACPowerMode, PowerSetUserConfiguredACPowerMode function, base.powersetuserconfiguredacpowermode, powersetting/PowerSetUserConfiguredACPowerMode, powrprof/PowerSetUserConfiguredACPowerMode
req.header: powersetting.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11 [desktop apps only]
req.target-min-winversvr: Windows Server 23H2 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: powrprof.lib
req.dll: powrprof.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 23H2
f1_keywords:
 - PowerSetUserConfiguredACPowerMode
 - powersetting/PowerSetUserConfiguredACPowerMode
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - powrprof.dll
 - api-ms-win-power-setting-l1-1-0.dll
api_name:
 - PowerSetUserConfiguredACPowerMode
---

# PowerSetUserConfiguredACPowerMode function

## -description

Update the user configured power mode setting for when the device is in an AC (adapter/charge) supply state.

## -parameters

### -param PowerModeGuid [in]

A pointer to a GUID buffer that specifies the user configured power mode.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="GUID_POWER_MODE_BEST_EFFICIENCY"></a><a id="guid_power_mode_best_efficiency"></a><dl>
<dt><b>GUID_POWER_MODE_BEST_EFFICIENCY</b></dt>
<dt>961cc777-2547-4f9d-8174-7d86181b8a7a</dt>
</dl>
</td>
<td width="60%">
Select this power mode to bias towards device energy efficiency.

</td>
</tr>
<tr>
<td width="40%"><a id="GUID_POWER_MODE_NONE"></a><a id="guid_power_mode_none"></a><dl>
<dt><b>GUID_POWER_MODE_NONE</b></dt>
<dt>00000000-0000-0000-0000-000000000000</dt>
</dl>
</td>
<td width="60%">
Select this power mode for a balance between performance and energy efficiency.

</td>
</tr>
<tr>
<td width="40%"><a id="GUID_POWER_MODE_BEST_PERFORMANCE"></a><a id="guid_power_mode_best_performance"></a><dl>
<dt><b>GUID_POWER_MODE_BEST_PERFORMANCE</b></dt>
<dt>ded574b5-45a0-4f42-8737-46345c09c238</dt>
</dl>
</td>
<td width="60%">
Select this power mode to bias towards device performance.

</td>
</tr>
</table>

## -returns

If the function succeeds, it returns <b>ERROR_SUCCESS</b>. If the function fails, it returns a system error code.

## -remarks

Supports the configuration of the user configured power mode using the default power modes provided inbox.

The user configured power mode is designed as a vote on system behavior from the user. It can be overridden by other system signals. Calling this setter API will immediately update the user configured power mode, and the system internals will immediately check if the effective power mode can also be updated. If there are no other signals overriding the user configured power mode, then it will become the effective power mode, and its setting values will be applied to the runtime system state.

Power modes were previously referred to as "overlays" or "overlay schemes".

## -see-also

<a href="/windows/desktop/Power/power-management-functions">Power Management Functions</a>
