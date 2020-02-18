cmake_minimum_required(VERSION 3.13)
project(Nes_Snd_Emu)

set(CMAKE_CXX_STANDARD 98)

include_directories(/usr/local/include /usr/local/include/SDL .)
link_directories(/usr/local/lib)

project(sdl_audio)
find_package(SDL)
find_library(COCOA_LIBRARY Cocoa)

set(SOURCE_FILES Simple_Apu.cpp Sound_Queue.cpp Wave_Writer.cpp Wave_Writer.hpp nes_apu/apu_snapshot.cpp nes_apu/apu_snapshot.h nes_apu/blargg_common.h nes_apu/blargg_source.h nes_apu/Blip_Buffer.cpp nes_apu/Blip_Buffer.h nes_apu/Blip_Synth.h nes_apu/Multi_Buffer.cpp nes_apu/Multi_Buffer.h nes_apu/Nes_Apu.cpp nes_apu/Nes_Apu.h nes_apu/Nes_Namco.cpp nes_apu/Nes_Namco.h nes_apu/Nes_Oscs.cpp nes_apu/Nes_Oscs.h nes_apu/Nes_Vrc6.cpp nes_apu/Nes_Vrc6.h nes_apu/Nonlinear_Buffer.cpp nes_apu/Nonlinear_Buffer.h boost/config.hpp boost/cstdint.hpp boost/static_assert.hpp)

add_executable(demo demo.cpp ${SOURCE_FILES})
target_link_libraries(demo SDL SDLmain ${COCOA_LIBRARY})
