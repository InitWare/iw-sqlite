add_library(iw-sqlite sqlite3.c)
target_compile_definitions(iw-sqlite PRIVATE SQLITE_ENABLE_JSON1=1
    SQLITE_DQS=0
    SQLITE_DEFAULT_WAL_SYNCHRONOUS=1
    SQLITE_LIKE_DOESNT_MATCH_BLOBS
    SQLITE_MAX_EXPR_DEPTH=0
    SQLITE_OMIT_DECLTYPE
    SQLITE_OMIT_DEPRECATED
    SQLITE_OMIT_PROGRESS_CALLBACK
    SQLITE_OMIT_SHARED_CACHE
    SQLITE_USE_ALLOCA)
target_include_directories(iw-sqlite PUBLIC .)
target_link_libraries(iw-sqlite INTERFACE Threads::Threads ${CMAKE_DL_LIBS})