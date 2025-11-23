#!/usr/bin/env bash

LOW_LEVEL=15
CRITICAL_LEVEL=5
HIBERNATE_LEVEL=3

LEVEL=$(cat /sys/class/power_supply/BAT0/capacity)
STATUS=$(cat /sys/class/power_supply/BAT0/capacity)

notify_low(){
	notify-send -a "Battery" "Battery is low" -u critical
}

notify_critical(){
	notify-send -a "Battery" "Battery is critically low" -u critical
	
}

hibernate_computer(){
	notify-send -a "Battery" "Hibernating due to critical battery!" -u critical
    	sleep 5
    	ZZZ
}

if [[ "$STATUS" = "Discharging" ]]; then

	if [[ "$LEVEL" -le "$HIBERNATE_LEVEL" ]]; then
		hibernate_computer
	elif [[ "$LEVEL" -le "$CRITICAL_LEVEL" ]]; then
		notify_critical
	elif [[ "$LEVEL" -le "$LOW_LEVEL" ]]; then
		notify_low
	fi
fi

