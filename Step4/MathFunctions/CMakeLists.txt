add_library(MathFunctions mysqrt.cxx)

# state that anybody linking to us needs to include the current source dir
# to find MathFunctions.h, while we don't.
target_include_directories(MathFunctions
          INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}
          )

add_library(mathfunctions_compiler_flags INTERFACE)
target_compile_features(mathfunctions_compiler_flags INTERFACE cxx_std_20)

# TODO 3: Link to tutorial_compiler_flags
target_link_libraries(MathFunctions PUBLIC mathfunctions_compiler_flags)
