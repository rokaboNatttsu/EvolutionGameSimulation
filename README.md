# パラメータ

ROUND：行動の繰り返し数。

SQR：2次元正方形領域の辺の長さ。正の整数限定。デフォルト=20

AGENT_NUM：エージェント数。正の整数限定。デフォルト=1000

ASSEMBLY_PARAM：エージェントが、人口密度の大きい方向に移動する傾向を決める。大きい値ほど、人口密度の高いほうに向かいやすい。正の実数限定。デフォルト=1

PRESSHURE_2_CENTER：2次元平面上の中央に向かって移動する傾向。0のとき、中央に向かう傾向がなくなる。二次元平面領域には端っこがり、この値を0より大きくしておかないと、エージェントが端に偏る傾向がある。制の実数限定。デフォルト=0.01

TMGR_WAIGHT：T＝Taker、M＝Matcher、G＝Giver、R＝Random、の順で初期の戦略の確立を指定する。0を指定すると、その戦略は存在しないものとして扱う。デフォルト=[1/4,1/4,1/4,1/4]

STRATEGY_SHIFT：「エージェントが途中で確率的に戦略を変える可能性」の有無を指定。Trueのとき、エージェントは確率的に戦略を変え、Falseのとき、各エージェントの戦略は固定される。デフォルト=True

PENALTY_LINE：r = 「略奪行動をとったエージェント数」÷(「略奪行動をとったエージェント数」ー「協力行動をとったエージェント数」)　でrを定義したとき、r < PENALTY_LINE の集団では、略奪行動をとったエージェントがペナルティを受ける。デフォルトでは、ペナルティは存在しない。

# 各戦略

taker：常に略奪する。あだ名は「略奪者」

matcher：ほかのエージェントの行動の多数派に追従する戦略。すなわち、前回協力したエージェントが多ければ今回協力し、前回略奪したエージェントが多ければ今回略奪する。あだ名は「キョロ充」

giver：常に協力する。あだ名は「間抜け」

random：協力することもあれば略奪することもある。周りのエージェントの行動と関係なくランダムに自身の行動を選択する。あだ名は「気分屋」。



# 共通で追加したい機能(オプション)

・コミュニティ毎に戦略の割合に依存したパラメータを導入し、このパラメータを損得計算に使う。パラメータ→損得→支配的戦略→パラメータ　というループフィードバックになるように。

# 他

・Cooporationが多い集団ほど成長し、成長した集団内ではCompetitonが盛んになり、Competitionが盛んだと集団が衰退し、衰退する集団からは多くのエージェントが流出し、流出したエージェントは新たな集団の構成員になる」という一連の流れが再現されることになると思われる。コミュニティが唯一無二になるような条件では停滞が見られ、新しいコミュニティができては消えていく条件では停滞する集団と躍進する集団がある、という状態。

・各種パラメータを変化させ、条件と適応的な戦略の対応関係を見ていくことができるように、改善する。以下のような条件でシミュレーションできるようにしたい。

