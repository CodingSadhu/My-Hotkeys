#SingleInstance Force
#InputLevel 0
;Once I deleted a file that meant life to me
+Del::
KeyWait Shift
Send {Delete}
return 

#n::
FileAppend, , C:\Users\Rathore\Desktop\Buffer.txt
 Run, Notepad.exe C:\Users\Rathore\Desktop\Buffer.txt
return

;-----------------------MultiClipBoard End----------------------
^Numpad1::Cut(1)
^Numpad4::Copy(1)
^Numpad7::Paste(1)

^Numpad2::Cut(2)
^Numpad5::Copy(2)
^Numpad8::Paste(2)

^Numpad3::Cut(3)
^Numpad6::Copy(3)
^Numpad9::Paste(3)

Copy(clipboardID)
{
	global ; All variables are global by default
	local oldClipboard := ClipboardAll ; Save the (real) clipboard
	
	Clipboard = ; Erase the clipboard first, or else ClipWait does nothing
	Send ^c
	ClipWait, 2, 1 ; Wait 1s until the clipboard contains any kind of data
	if ErrorLevel 
	{
		Clipboard := oldClipboard ; Restore old (real) clipboard
		return
	}
	
	ClipboardData%clipboardID% := ClipboardAll
	
	Clipboard := oldClipboard ; Restore old (real) clipboard
}

Cut(clipboardID)
{
	global ; All variables are global by default
	local oldClipboard := ClipboardAll ; Save the (real) clipboard
	
	Clipboard = ; Erase the clipboard first, or else ClipWait does nothing
	Send ^x
	ClipWait, 2, 1 ; Wait 1s until the clipboard contains any kind of data
	if ErrorLevel 
	{
		Clipboard := oldClipboard ; Restore old (real) clipboard
		return
	}
	ClipboardData%clipboardID% := ClipboardAll
	
	Clipboard := oldClipboard ; Restore old (real) clipboard
}

Paste(clipboardID)
{
	global
	local oldClipboard := ClipboardAll ; Save the (real) clipboard

	Clipboard := ClipboardData%clipboardID%
	Send ^v

	Clipboard := oldClipboard ; Restore old (real) clipboard
	oldClipboard = 
}

;-----------------------MultiClipBoard End----------------------

>^NumpadAdd:: Send {Volume_Down}
>^NumpadSub:: Send {Volume_Up}
>^NumpadMult:: Send {Volume_Mute}


^+d::Run, "F:\Downloads"
return

^+a::WinSet, AlwaysOnTop, toggle, A
return

^+i::Run, "D:\Anki2.1\Anki\anki.exe"
return

^!c::Run,calc.exe
return

^!s::Run,"C:\Users\Nishit Rathore\Pictures\Screenshots"
return

^!n::Run, "D:\Notepad++\notepad++.exe"
return

#c::
Run, cmd.exe
return

PrintScreen::Send, {LWin Down}{PrintScreen}{LWin Up}
return

~Shift & WheelUp::  ; Scroll left
  ControlGetFocus, fcontrol, A
  Loop 6  ; <-- Increase this value to scroll faster.
    SendMessage, 0x114, 0, 0, %fcontrol%, A  ; 0x114=WM_HSCROLL; 0=SB_LINELEFT
return

~Shift & WheelDown::  ; Scroll right
  ControlGetFocus, fcontrol, A
  Loop 6  ; <-- Increase this value to scroll faster.
    SendMessage, 0x114, 1, 0, %fcontrol%, A  ; 0x114=WM_HSCROLL; 1=SB_LINERIGHT
return

;~Pause::
;Suspend ; Assign the toggle-suspend function to a hotkey.
;return

;Toggles the title bar of a window
#t::
WinSet, Style, ^0xC00000, A
return 

;anki me jo me vo color karta tha wo
`::
#IfWinActive, Edit Current
Send, {CtrlDown}{b}{CtrlUp}
Send, {F7}
return
