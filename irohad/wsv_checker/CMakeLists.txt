#
# Copyright Soramitsu Co., Ltd. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0
#

set(CMAKE_CXX_STANDARD 20)
add_executable(wsv_checker wsv_checker.cpp)
#target_compile_features(wsv_checker PUBLIC cxx_std_20)
#target_compile_options(wsv_checker PUBLIC -Werror -Wno-error=unused-variable)
target_link_libraries(wsv_checker PRIVATE
        gflags
        logger_manager
        ametsuchi
        )

find_package(nlohmann_json CONFIG REQUIRED)
target_link_libraries(wsv_checker PRIVATE nlohmann_json nlohmann_json::nlohmann_json)
