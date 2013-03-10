# keyboard shortcuts

Adaptado a las teclas de desplazamiento de vim (h, j, k, l)

    <keyboard>

      <!-- lxde -->

      <keybind key="A-C-BackSpace">
        <action name="Execute">
          <command>lxlogout</command>
        </action>
      </keybind>

      <keybind key="A-C-Delete">
          <action name="Execute">
              <command>lxtask</command>
          </action>
      </keybind>

      <keybind key="A-Escape">
        <action name="Execute">
              <command>lxpanelctl menu</command>
        </action>
      </keybind>

      <keybind key="A-r">
        <action name="Reconfigure"/>
      </keybind>

      <keybind key="A-q">
        <action name="Restart"/>
      </keybind>

      <keybind key="A-x">
        <action name="Execute">
          <command>lxlock</command>
        </action>
      </keybind>

      <keybind key="Print">
        <action name="Execute">
          <command>
            scrot &quot;%Y%m%d.png&quot; -e &quot;mv $f ~/Desktop&quot;
          </command>
        </action>
      </keybind>

      <!-- desktop -->

      <keybind key="C-A-l">
        <action name="DesktopRight"/>
      </keybind>

      <keybind key="C-A-h">
        <action name="DesktopLeft"/>
      </keybind>

      <keybind key="A-1">
        <action name="Desktop">
          <desktop>1</desktop>
        </action>
      </keybind>

      <keybind key="A-2">
        <action name="Desktop">
          <desktop>2</desktop>
        </action>
      </keybind>

      <keybind key="A-3">
        <action name="Desktop">
          <desktop>3</desktop>
        </action>
      </keybind>

      <keybind key="A-4">
        <action name="Desktop">
          <desktop>4</desktop>
        </action>
      </keybind>

      <!-- window -->

      <keybind key="A-c">
        <action name="Close"/>
      </keybind>

      <keybind key="S-C-A-l">
        <action name="SendToDesktopRight"/>
      </keybind>

      <keybind key="S-C-A-h">
        <action name="SendToDesktopLeft"/>
      </keybind>

      <keybind key="A-space">
        <action name="ToggleMaximizeVert"/>
      </keybind>

      <keybind key="S-A-space">
        <action name="ToggleMaximizeFull"/>
      </keybind>

      <keybind key="A-h">
        <action name="MoveToEdgeWest"/>
      </keybind>

      <keybind key="A-l">
        <action name="MoveToEdgeEast"/>
      </keybind>

      <keybind key="A-k">
        <action name="MoveToEdgeNorth"/>
      </keybind>

      <keybind key="A-j">
        <action name="MoveToEdgeSouth"/>
      </keybind>

      <keybind key="A-Tab">
        <action name="NextWindow"/>
      </keybind>

      <keybind key="S-A-Tab">
        <action name="PreviousWindow"/>
      </keybind>

      <!-- launchers -->

      <keybind key="A-p">
        <action name="Execute">
          <command>run</command>
        </action>
      </keybind>

      <!-- apps -->

      <keybind key="A-Return">
        <action name="Execute">
          <command>lxterminal</command>
        </action>
      </keybind>

      <keybind key="A-f">
        <action name="Execute">
          <command>pcmanfm</command>
        </action>
      </keybind>

    </keyboard>
