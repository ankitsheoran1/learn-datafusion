Datafusion is an in memory query engine that uses Apache Arrow as query Model 

Datafusion frontend = SQLStatement 
Intermediate Query Representation = LogicalPlan Expr 
Conceret Execution = ExecutionPlan RecordBatches

Datafusion Logical plan creation =
Declarative(Describe what you want) OR Procedural(Describe How directly => Rust take logicalplanbuilder or DataFrame module popularized by pandas )

Built IN Datafusion Optimizer Passes 
 ProjectionPushDown(Minimize numbe rof column passed from node to node to minimize intermediate result size)
 FilterPushDown(predicate pushdown) push filters as close to scan as possible to minimize intermediate result size 
 HashBuildProbeOrder(join reordering) Order joins to minimize intermediate result size and hash table size 
 ConstantFolding Partial Evaluate Expression at Plan Time Ex ColA && true => ColA