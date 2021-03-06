set(LLVM_LINK_COMPONENTS
  Option
  Support
  )

add_subdirectory(Core)
add_subdirectory(Refactor)
add_subdirectory(Refactoring)
add_subdirectory(ASTDiff)

add_clang_library(clangTooling
  ArgumentsAdjusters.cpp
  CommonOptionsParser.cpp
  CompilationDatabase.cpp
  Execution.cpp
  FileMatchTrie.cpp
  FixIt.cpp
  JSONCompilationDatabase.cpp
  Refactoring.cpp
  RefactoringCallbacks.cpp
  StandaloneExecution.cpp
  Tooling.cpp

  DEPENDS
  ClangDriverOptions

  LINK_LIBS
  clangAST
  clangASTMatchers
  clangBasic
  clangDriver
  clangFormat
  clangFrontend
  clangLex
  clangRewrite
  clangToolingCore
  clangToolingRefactor
  clangToolingRefactoring
  )
