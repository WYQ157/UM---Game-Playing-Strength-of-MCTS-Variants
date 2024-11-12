train.csv字段解释
Id：每行数据的唯一ID，可忽略。
GameRulesetName：游戏名称和规则的组合。例如，同一游戏可能有多个规则集。
agent[1/2]：描述每个参与者的代理（agent）名称。
EnglishRules：游戏规则的英文描述，不保证完整。
LudRules：使用Ludii语言描述的游戏规则，确保了描述的完整性和准确性。
num_wins_agent1、num_draws_agent1、num_losses_agent1：第一个代理对战中的胜、平、负次数。
utility_agent1：目标字段，表示第一个代理的效用值，范围为-1到1，反映了该代理的表现强度。

test.csv字段
与train.csv相同，但不包含num_wins_agent1、num_draws_agent1、num_losses_agent1和utility_agent1字段。测试集包含约6万条隐藏测试集数据。

sample_submission.csv字段
Id：唯一ID，与test.csv匹配。
utility_agent1：目标预测值，应在-1到1之间。
concepts.csv字段
Id：概念的唯一ID。
Name：概念的名称。
Description：概念的简要说明。
TypeId、DataTypeId、ComputationTypeId：概念的类型、数据类型和计算类型。
TaxonomyString：概念在层级分类中的位置。
LeafNode、ShowOnWebsite：是否为分类叶节点及是否在Ludii网站展示。
代理（agent）名称格式
代理名称格式为MCTS-<SELECTION>-<EXPLORATION_CONST>-<PLAYOUT>-<SCORE_BOUNDS>，例如MCTS-UCB1GRAVE-0.1-NST-true。各部分解释：

SELECTION：MCTS算法选择策略。
EXPLORATION_CONST：探索常数，调整探索与利用的权衡。
PLAYOUT：MCTS的play-out策略。
SCORE_BOUNDS：是否使用得分边界版本的MCTS。
