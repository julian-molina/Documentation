trading_engine: "The trading engine hierarchy is the data structure used by the trading bot to keep runtime information highly accessible and exposed to others. Trading systems may access the information processed by the trading bot, keep track of and react to current and past events&mdash;including those involving the exchange, such as orders placed or filled&mdash;as the bot is running."

current: "The current object stores instances of several other objects, in particular the instances that are open at the time of evaluation. Conceptually, current is used as an adverb of time applied to different concepts, such as the current episode, the current strategy, the current position, or the current strategy stage."

episode: "Episode is the object that handles the information corresponding to the whole run of the trading bot&mdash;beginning to end&mdash;between the specified initial datetime and final datetime in the time range parameter of a trading session."

serial_number: "Serial number is a sequential number assigned to the object represented by the parent node at the moment it's opened."

identifier: "Identifier is a unique alphanumeric string by which the object represented by the parent node may be unequivocally identified."

begin: "Begin is the datetime at the moment the object represented by the parent node began to exist."

end: "End is the datetime on which the object represented by the parent node ceased to exist. In case the object hasn't been closed yet, it is the datetime at the moment of evaluation."

begin_rate: "Begin rate is the close rate of the candle corresponding to the datetime of the begin property."

end_rate: "End rate is the close rate of the candle corresponding to the datetime of the end property."

status: "Status refers to the state of the object represented by the parent node at the moment of evaluation."

exit_type: "Exit type refers to the reason why the object is closed."

episode_base_asset: "The episode base asset node keeps track of the evolution of variables related to the base asset throughout the episode."

balance: ""

begin_balance: ""

end_balance: ""

hits: "Hits counts the number of positions that closed with a positive profit loss (P&L), in the context of the parent node."

fails: "Fails counts the number of positions that closed with a negative profit loss (P&L), in the context of the parent node."

hit_ratio: "Hit ratio is the percentage of positions that closed with a positive profit loss (P&L), in the context of the parent node."

profit_loss: ""

roi: ""

annualized_rate_of_return: ""

hit_fail: ""

episode_quoted_asset: "The episode quoted asset node keeps track of the evolution of variables related to the quoted asset throughout the episode."

episode_counters: "The episode counters node features counters of instances of objects that come to exist during the duration of the episode."

periods: "Periods counts the number of candles that have been evaluated, in the context of the parent node."

strategies: "Strategies counts the number of times strategies have been triggered-on, in the context of the parent node."

positions: "Positions counts the number of times positions have been opened, in the context of the parent node."

orders: "Orders counts the number of times orders have been placed, in the context of the parent node."

user_defined_counters: ""

episode_statistics: "Episode statistics keeps track of several metrics in the context of the episode."

days: "Days counts the number of days through which the trading bot has cycled since the object represented by the parent node was open."

user_defined_statistic: "A user defined statistic allows users to create custom metrics by defining the corresponding calculation in a formula, in the context of the parent node."

formula: "A formula is a mathematical expression intended to determine a numerical value to be applied dynamically to a certain property."

candle: "Candle features all the properties that make up a candle."

open: "Open is the rate at the datetime of the begin property, as provided by the exchange. That is, the rate at the open of the candle."

close: "Close is the rate at the datetime of the end property, as provided by the exchange. That is, the rate at the close of the candle."

min: "Min is the minimum rate registered by the exchange during the period between the datetimes of the begin and end properties, as provided by the exchange."

max: "Max is the maximum rate registered by the exchange during the period between the datetimes of the begin and end properties, as provided by the exchange."

index: "Index is the position of the parent object in the corresponding data collection, as determined by the context."

distance_to_event: "Distance to event features counters indicating how many periods (candles) have passed since the last occurrence of certain events."

trigger_on: "Counts the periods since the last time a strategy was triggered on."

trigger_off: "Counts the periods since the last time a strategy was triggered off."

take_position: "Counts the periods since the last time a position was taken."

close_position: "Counts the periods since the last time a position was closed."

next_phase: "Counts the periods since the last time a next phase event was triggered."

move_to_phase: "Counts the periods since the last time a move to phase event was triggered."

create_order: "Counts the periods since the last time an order was created."

cancel_order: "Counts the periods since the last time an order was canceled."

close_order: "Counts the periods since the last time an order was closed."

strategy: "Strategy is the section of the data structure that keeps track of information within the scope of the trading strategy as defined in the trading system, during the time the strategy is open."

situation_name: "Situation name features the name of the situation that triggered a certain event, which is dependent on the context."

strategy_name: "Strategy name features the name of the strategy that is currently open."

strategy_counters: "The strategy counters node features counters of instances of objects that come to exist while the strategy is open."

position: "Position is the section of the data structure that keeps track of information within the scope of each position, and during the time a position is open."

entry_target_rate: "Entry target rate is the target rate set on the initial targets definition, in the open stage of the strategy."

exit_target_rate: "Exit target rate is the target rate set on the initial targets definition, in the close stage of the strategy."

stop_loss: "Stop loss is the current stop loss target, as defined in the manage stage of the corresponding strategy."

stop_loss_phase: "Stop loss phase is the numeric value of the phase that is currently open, and thus, defining the value of the stop loss."

stop_loss_position: "Stop Loss position indicates if the stop loss target is above or below the position rate."

take_profit: "Take profit is the current take profit target, as defined in the manage stage of the corresponding strategy."

take_profit_phase: "Take profit phase is the numeric value of the phase that is currently open, and thus, defining the value of the take profit."

take_profit_position: "Take profit position indicates if the take profit target is above or below the position rate."

position_counters: "The position counters node features counters of instances of objects that come to exist during the duration of the position."

position_statistics: "Position statistics keeps track of several metrics in the context of the position."

position_base_asset: "The position base asset node keeps track of the evolution of variables related to the base asset throughout the position."

entry_target_size: "Entry target size is the target size set on the initial targets definition, in the open stage of the strategy."

exit_target_size: "Exit target size is the target size set on the initial targets definition, in the close stage of the strategy."

position_quoted_asset: "The position quoted asset node keeps track of the evolution of variables related to the quoted asset throughout the position."

strategy_trigger_stage: "Strategy trigger stage is the section of the data structure that keeps track of information specific to the scope of the trigger stage during the period the stage is open."

strategy_open_stage: "Strategy open stage is the section of the data structure that keeps track of information specific to the scope of the open stage during the period the stage is open."

stage_base_asset: "The stage base asset node keeps track of the evolution of variables related to the base asset throughout the stage."

target_size: ""

size_placed: ""

size_filled: ""

fees_paid: ""

stage_quoted_asset: "The stage quoted asset node keeps track of the evolution of variables related to the quoted asset throughout the stage."

strategy_manage_stage: "Strategy manage stage is the section of the data structure that keeps track of information specific to the scope of the manage stage during the period the stage is open."

strategy_close_stage: "Strategy close stage is the section of the data structure that keeps track of information specific to the scope of the close stage during the period the stage is open."

last: ""

exchange_orders: ""

market_buy_orders: ""

market_order: ""

exchange_id: ""

rate: ""

order_name: ""

algorithm_name: ""

order_counters: ""

lock: ""

order_base_asset: ""

size: ""

order_quoted_asset: ""

order_statistics: ""

percentage_filled: ""

actual_rate: ""

market_sell_orders: ""

limit_buy_orders: ""

limit_order: ""

limit_sell_orders: ""

dynamic_indicators: ""

indicator_function: ""