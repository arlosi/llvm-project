add_mlir_dialect_library(MLIRLLVMIR
  IR/LLVMDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR
  )
add_dependencies(MLIRLLVMIR MLIRLLVMOpsIncGen MLIRLLVMConversionsIncGen LLVMAsmParser LLVMCore LLVMSupport)
target_link_libraries(MLIRLLVMIR LLVMAsmParser LLVMCore LLVMSupport MLIRIR)

add_mlir_dialect_library(MLIRNVVMIR
  IR/NVVMDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR
  )
add_dependencies(MLIRNVVMIR MLIRNVVMOpsIncGen MLIRNVVMConversionsIncGen LLVMAsmParser LLVMCore LLVMSupport)
target_link_libraries(MLIRNVVMIR LLVMAsmParser MLIRIR MLIRLLVMIR LLVMSupport LLVMCore)

add_mlir_dialect_library(MLIRROCDLIR
  IR/ROCDLDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR
  )
add_dependencies(MLIRROCDLIR MLIRROCDLOpsIncGen MLIRROCDLConversionsIncGen LLVMAsmParser LLVMCore LLVMSupport)
target_link_libraries(MLIRROCDLIR LLVMAsmParser LLVMCore LLVMSupport MLIRIR)
