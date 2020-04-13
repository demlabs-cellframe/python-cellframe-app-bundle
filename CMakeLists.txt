cmake_minimum_required(VERSION 2.8)
#project(CellFrame C)
if (OS_TYPE_DESKTOP)
#add_executable(CellframeApp main.c)
set(NODE_TARGET      "${PROJECT_NAME}"     )
set(NODE_CLI_TARGET  "${PROJECT_NAME}-cli" )
set(NODE_TOOL_TARGET "${PROJECT_NAME}-tool")
set( NODE_SOURCES
  sources/main.c
  sources/sig_unix_handler.c
)
set( NODE_CLI_SOURCES
  sources/main_node_cli.c
)
set( NODE_TOOL_SOURCES
  sources/main_node_tool.c
)

endif()

if(ANDROID)
  add_library(${PROJECT_NAME} SHARED
        ${NODE_SOURCES}
        ${NODE_CLI_SOURCES}
        ${NODE_TOOL_SOURCES}
        sources/cellframe_node.h
    )
endif()
