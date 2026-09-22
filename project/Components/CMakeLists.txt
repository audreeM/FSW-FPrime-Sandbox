# Include project-wide components here

# add_fprime_subdirectory("${CMAKE_CURRENT_LIST_DIR}/MyComponent/")
add_fprime_subdirectory("${CMAKE_CURRENT_LIST_DIR}/HiComponent/")

# The deployment registers itself with register_fprime_zephyr_deployment, which
# only exists when the Zephyr library is loaded, and its topology pulls in
# Zephyr-only drivers. Unit tests build against F Prime's native OS layer, so
# under BUILD_TESTING build the testable components instead of the deployment.
if (BUILD_TESTING)
    add_fprime_subdirectory("${CMAKE_CURRENT_LIST_DIR}/MAX17205/")
else()
    add_fprime_subdirectory("${CMAKE_CURRENT_LIST_DIR}/FirstDeployment/")
endif()
