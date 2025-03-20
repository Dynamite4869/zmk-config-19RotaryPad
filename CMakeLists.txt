cmake_minimum_required(VERSION 3.13.1)

# プロジェクト名
project(zmk_config VERSION 0.1 LANGUAGES C CXX)

# Zephyrの設定をインクルード
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})

# 必要なZMKのディレクトリをインクルード
include_directories(${ZMK_INCLUDE_DIRS})

# 使用するシールドの指定
set(SHIELD 19RotaryPad)

# シールドの設定ファイルをインクルード
include(${CMAKE_SOURCE_DIR}/config/shields/19RotaryPad.overlay)

# 使用するボードの設定
set(BOARD seeeduino_xiao_ble)



# キーマップの設定
set(ZMK_KEYMAP_FILE "\config\boards\shields\19RotaryPad")

# ZMKアプリケーションを追加
add_subdirectory(zmk)
