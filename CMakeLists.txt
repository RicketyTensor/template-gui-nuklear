project(nuklear_app)
cmake_minimum_required(VERSION 3.22)

# =============================================================================
# Global settings
# =============================================================================
set(SRC_DIR ${CMAKE_SOURCE_DIR}/src)
set(NUKLEAR_DIR ${CMAKE_SOURCE_DIR}/external/nuklear)

# =============================================================================
# Select framework
# =============================================================================
set(BACKEND glfw)
set(RENDERER opengl3)

# =============================================================================
# Select source files
# =============================================================================
set(SOURCES
    ${SRC_DIR}/frameworks/${BACKEND}_${RENDERER}.c
)

# =============================================================================
# Set build instructions
# =============================================================================
add_executable(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME} PUBLIC glfw m GL GLU GLEW )
target_include_directories(${PROJECT_NAME} PUBLIC ${NUKLEAR_DIR})
