trading_system: "A trading system is a framework handling the low-level logic that serves to structure the processes and methods used to implement and deploy trading strategies."

trading_strategy: "A strategy is a set of actions occurring in stages, designed to achieve a specific goal within a broader plan, via executing trades."

trigger_stage: "The trigger stage deals with monitoring the market in search of trading opportunities with the corresponding strategy."

trigger-on_event: "The trigger-on event defines the set of rules that need to be met for the corresponding strategy to be triggered on. A strategy that is triggered may use all the capital available to the trading system, and prevents other strategies in the system from triggering."

situation: "A situation refers to a specific state of the market in which a certain event should take place, as defined by any number of conditions."

condition: "Conditions are rules within a situation. When all conditions under a situation validate true, then the situation gets validated as well, and the associated event is triggered."

trigger-off_event: "The trigger-off event defines the situation in which the corresponding strategy shall be triggered-off. A strategy that is triggered-off releases the capital in reserve and makes it available to other strategies in the trading system."

take_position_event: "The take position event defines the situation that needs to be met to take a position."

open_stage: "The open stage deals with all the definitions that make up a position, including the target rate and size, and the definitions concerning order execution."

initial_targets: "The initial targets node holds the most basic definitions about the position to be taken: the target rate and the target size."

target_rate: ""

formula: "A formula is a mathematical expression intended to determine a numerical value to be applied dynamically to a certain property."

target_size_in_base_asset: ""

target_size_in_quoted_asset: ""

open_execution: ""

execution_algorithm: ""

market_buy_order: ""

create_order_event: ""

simulated_exchange_events: ""

simulated_partial_fill: ""

simulated_actual_rate: ""

simulated_fees_paid: ""

market_sell_order: ""

limit_buy_order: ""

order_rate: ""

limit_sell_order: ""




initial_definition: "The initial definition node groups the parameters that define the trade at the moment the position is taken."

initial_stop: "The initial stop defines the initial target to stop a loss before the trade gets to be managed."

initial_take_profit: "The initial take profit defines the initial target to take profit before the trade gets to be managed."

position_size: "The size of the position is the amount of capital that will go in the trade, denominated in the quoted asset. The position size node allows setting a size for the position using a formula."

position_rate: "The position rate is the rate at which the position is taken, denominated in the quoted asset. The position rate node allows setting the desired position rate with a formula."






manage_stage: "The manage stage deals with the setting and management of stop loss and take-profit targets."

managed_stop_loss: "The stop node in the manage stage groups all phases managing stop loss targets as the trade develops."

phase_0: "Phase 0 represents the starting point for a stop or take profit target, which may be managed in subsequent phases, on the manage stage."

phase_1: "Phase 1 is the first phase in the management of a stop or take-profit target. The management of targets may have as many phases as required."

next_phase_event: "The next-phase event is defined by a market situation upon which the management of the trade should shift from one phase to the next phase in a predetermined sequence."

move_to_phase_event: "The move-to-phase event is defined by a market situation upon which the management of the trade should shift from the current phase to an arbitrary phase, determined by a reference."

managed_take_profit: "Take profit node in the manage stage groups all phases managing take profit targets as the trade develops."

close_stage: "The close stage deals with all the definitions required to close a position, including the target rate and size, and the definitions concerning order execution."

close_execution: "Close execution is the node that will eventually hold the information regarding the execution of the closing orders."

event: "An event is an action triggered by predefined market situations."

javascript_code: "The JavaScript code node may hold any snippet of valid JavaScript."