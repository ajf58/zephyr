#
# Copyright (c) 2024 Nordic Semiconductor ASA
#
# SPDX-License-Identifier: Apache-2.0
#

cmake_minimum_required(VERSION 3.20.0)

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})

if(NOT (CONFIG_BOARD_NRF54H20DK_NRF54H20_CPUAPP))
  message(FATAL_ERROR "${BOARD}${BOARD_QUALIFIERS} is not supported for this sample")
endif()

project(nrf_coresight_stm)

target_sources(app PRIVATE $ENV{ZEPHYR_BASE}/samples/boards/nordic/coresight_stm/src/main.c)
