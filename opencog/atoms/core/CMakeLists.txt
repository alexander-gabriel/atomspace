
# The atom_types.h file is written to the build directory
INCLUDE_DIRECTORIES( ${CMAKE_CURRENT_BINARY_DIR})

ADD_LIBRARY (atomcore
	ArityLink.cc
	Checkers.cc
	CondLink.cc
	Context.cc
	DefineLink.cc
	DeleteLink.cc
	FindUtils.cc
	FreeLink.cc
	FunctionLink.cc
	ImplicationScopeLink.cc
	LambdaLink.cc
	NumberNode.cc
	PrenexLink.cc
	PresentLink.cc
	PutLink.cc
	Quotation.cc
	RandomChoice.cc
	RandomNumber.cc
	RewriteLink.cc
	ScopeLink.cc
	SleepLink.cc
	StateLink.cc
	TimeLink.cc
	TruthValueOfLink.cc
	TypedAtomLink.cc
	TypeNode.cc
	TypeUtils.cc
	UniqueLink.cc
	UnorderedLink.cc
	ValueOfLink.cc
	Variables.cc
	VariableList.cc
	VariableSet.cc
)

# Without this, parallel make will race and crap up the generated files.
ADD_DEPENDENCIES(atomcore opencog_atom_types)

TARGET_LINK_LIBRARIES(atomcore
	atombase
	${COGUTIL_LIBRARY}
)

INSTALL (TARGETS atomcore EXPORT AtomSpaceTargets
	DESTINATION "lib${LIB_DIR_SUFFIX}/opencog"
)

INSTALL (FILES
	ArityLink.h
	CondLink.h
	Context.h
	DefineLink.h
	DeleteLink.h
	FindUtils.h
	FreeLink.h
	FunctionLink.h
	LambdaLink.h
	NumberNode.h
	PrenexLink.h
	PresentLink.h
	PutLink.h
	Quotation.h
	RandomChoice.h
	RandomNumber.h
	RewriteLink.h
	ScopeLink.h
	SleepLink.h
	StateLink.h
	TimeLink.h
	TruthValueOfLink.h
	TypedAtomLink.h
	TypeNode.h
	TypeUtils.h
	UniqueLink.h
	UnorderedLink.h
	ValueOfLink.h
	Variables.h
	VariableList.h
	VariableSet.h
	DESTINATION "include/opencog/atoms/core"
)
