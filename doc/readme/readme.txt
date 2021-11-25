Example for making coerce:
Files for the project: (This is for that the default is not suitable for your board,
     also it had been done in dm9051_d1.c, dm9051_d2.c, dm9051_d3.c)
    ./dm_build_hardcore/d1_conf_ver.h
    ./dm_build_hardcore/d2_conf_ver.h
    ./dm_build_hardcore/d3_conf_ver.h
    ./dm_build_hardcore/dm_build_hardcore.h (macro definitions)
    ./dm_build_hardcore/ev_disable/dm_dts_develm13_collect.c
    ./dm_build_hardcore/ev_disable/dm_ndts_m7_collect.c
    ./dm_build_hardcore/opt/fn_ndts_redesigni_collect.c
    ./dm_build_hardcore/opt/func_redesignp_subroutine.h
    ./dm_build_hardcore/opt/func_redesignp_subroutine.c
    ./dm_build_hardcore/opt/fn_ndts_redesignp_collect.c
    ./dm_build_hardcore/opt/fn_dts_redesignp_collect.c
    ./dm_build_hardcore/dm_build_hardcore.c (include list structure)
    ./dm_coerces/dm9051_d1.c (in case to instead of original ./dm9051.c)
    ./dm_coerces/dm9051_d2.c (in case to instead of original ./dm9051.c)
    ./dm_coerces/dm9051_d3.c (in case to instead of original ./dm9051.c)
    ./dm_coerces/dm9051_olderkernel.c (in case to instead of original ./dm9051.c)

	#undef DM_TCONF_VER
	#define DM_TCONF_VER		3
	#include "dm_build_hardcore/dm_build_hardcore.h"
	#include "dm_build_hardcore/dm_build_hardcore.c"
	
	Note: In dm9051_d1.c, dm9051_d2.c, dm9051_d3.c, dm9051_olderkernel.c,
	 Add above selection support lines exactly before dm9051_init_dm9051() function.
	
Example for making support older kernel version:
Files for the project: (This is for the one who using the older kernel version, 
     also it had been done in dm9051_olderkernel.c)
    ./dm_build_hardcore/dm_build_olderkernel.h
    ./dm_coerces/dm9051_olderkernel.c (to instead of original ./dm9051.c)

	#include "dm_build_hardcore/dm_build_olderkernel.h"

	Note: In dm9051_olderkernel.c,
	 Add above selection support line nearly after #include "board_info.h" line.

Example for making debug-support:
Files for the project: (This is for add debug functions)
    ./dm_build_hardcore/board_info_debug_support.h (to instead of original ./board_info.h)
    ./dm_build_hardcore/debug_support/debug_code_rst_and_carri_collect.h
    ./dm_build_hardcore/debug_support/debug_code_rst_and_carri_collect.c

	#include "dm_build_hardcore/board_info_debug_support.h" 
	
	Note: In dm9051.c,
	 Add above above support line exactly instead of original #include "board_info.h" near the top.
	 
	#include "dm_build_hardcore/debug_support/debug_code_rst_and_carri_collect.h"
	#include "dm_build_hardcore/debug_support/debug_code_rst_and_carri_collect.c"

	Note: In dm9051.c,
	 Add above above support lines exactly before dm9051_init_dm9051() function.
