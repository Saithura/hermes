# Copyright (c) Facebook, Inc. and its affiliates.
#
# This source code is licensed under the MIT license found in the LICENSE
# file in the root directory of this source tree.

set(LLVM_LINK_COMPONENTS
  Analysis
  Core
  Support
  )

add_llvm_tool(hbc-diff
  hbc-diff.cpp
  ${ALL_HEADER_FILES}
  )

target_link_libraries(hbc-diff
  hermesVMRuntime
  hermesHBCBackend
  hermesSupport
  hermesInst
  ${CORE_FOUNDATION}
)

hermes_link_icu(hbc-diff)
