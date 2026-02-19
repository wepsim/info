

# Integrating WepSIM

<a name="wepsim-links"/>

## WepSIM Links in documents

In the WepSIM URL you can use several arguments to perform certain actions automatically.
This is an example:
<html>
<center>
 <h5>
 <table width="75%" border="2">
  <tr><td><a href="http://wepsim.github.io/wepsim/ws_dist/?mode=ep&amp;examples_set=RISCV&amp;example=0&amp;simulator=assembly:14&amp;notify=false">http://wepsim.github.io/wepsim/ws_dist/?mode=ep&amp;examples_set=RISCV&amp;example=0&amp;simulator=assembly:14&amp;notify=false</a></td></tr>
 </table>
 </h5>
 </center>
</html>

In particular, WepSIM supports the following arguments:
<html>
 <table border="1">
  <tr>
    <th>Name</th>
    <th>Included values</th>
    <th>Used for...</th>
   </tr>
    <tr>
    <td rowspan=4><i><b>mode</b></i></td>
    <td><i>ep</i></td>
    <td>Elemental Processor  with circuit and assembly (default)</td>
  </tr>
  <tr>
    <td><i>poc</i></td>
    <td>Proof-of-Concept  Processor with circuit and assembly</td>
  </tr>
  <tr>
    <td><i>asm_mips</i></td>
    <td>Elemental Processor (default) with MIPS assembly only</td>
  </tr>
  <tr>
    <td><i>asm_rv32</i></td>
    <td>Elemental Processor (default) with RISC-V assembly only</td>
  </tr>
  <tr>
    <td rowspan=4><i><b>config_set</b></i></td>
    <td><i>Desktop</i></td>
    <td>Interface for desktop computer (default)</td>
  </tr>
  <tr>
    <td><i>Mobile</i></td>
    <td>Interface for smartphone or tablet</td>
  </tr>
  <tr>
    <td><i>Desktop-Dark</i></td>
    <td>Interface for desktop computer and dark mode</td>
  </tr>
  <tr>
    <td><i>Mobile-Dark</i></td>
    <td>Interface for smartphone or tablet in dark mode</td>
  </tr>  
  <tr>
    <td rowspan=6><i><b>examples_set</b></i></td>
    <td><i>RISCV</i></td>
    <td>Examples for RISCV instruction set</td>
  </tr>
  <tr>
    <td><i>RISCV-Instructive</i></td>
    <td>Examples for RISCV instruction set with active comments</td>
  </tr>
    <tr>
    <td><i>MIPS</i></td>
    <td>Examples for MIPS instruction set</td>
  </tr>
  <tr>
    <td><i>MIPS-Instructive</i></td>
    <td>Examples for MIPS instruction set with active comments</td>
  </tr>
    <tr>
    <td><i>ARM</i></td>
    <td>Examples for ARM-like instruction set</td>
  </tr>
    <tr>
    <td><i>Z80</i></td>
    <td>Examples for Z80-like instruction set</td>
  </tr>
  <tr>
    <td rowspan=1><i><b>example</b></i></td>
    <td><i>0, 1, ...</i></td>
    <td>The indentifier of the example within the example set</td>
  </tr>
     <tr>
    <td rowspan=2><i><b>simulator</b></i></td>
    <td rowspan=2><i>&lt;main panel&gt;:&lt;details panel&gt;</i></td>
    <td>&lt;main panel&gt; can be:
    <ul>
    <li>microcode &rarr; to show the circuit panel.
    <li>assembly   &rarr; to show the assembly panel. 
    </ul>
    </td>
  </tr>
  <tr>
    <td>&lt;details panel&gt; can be:
       <ul>
       <li><i>registers</i>       &rarr; register file.
       <li><i>control_memory</i>  &rarr; control memory.
       <li><i>memory</i>          &rarr; memory.
       <li><i>keyboard</i>        &rarr; keyboard and screen.
       <li><i>ledmatrix</i>       &rarr; led-matrix.
       <li><i>3dled</i>           &rarr; 3d-led panel.
      </ul>
    </td>
  </tr>
  <tr>
    <td rowspan=1><i><b>checkpoint</b></i></td>
    <td><i>&lt;URL&gt;</i></td>
    <td>URL pointing to the checkpoint to be loaded</td>
  </tr>
  <tr>
    <td rowspan=2><i><b>notify</b></i></td>
    <td><i>true</i></td>
    <td>Show a dialog-box with the preloaded actions (default)</td>
  </tr>
  <tr>
    <td><i>false</i></td>
    <td>Don't show a dialog-box with the preloaded actions</td>
  </tr>
 </table>
</html>

But there is one more argument that can be added: ***asm***
***asm*** contains the assembly code to be loaded from the URL.

This assembly code can be obtained from the ***share*** option in the "Load/Save" dialog-box:
![screen:example1](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/simulator025.jpg)

This argument can be combined with the example argument so the assembly code in the URL is loaded instead of the assembly code in the example.

For example, the following link loads the RISC-V assembly code for the factorial and with the keyboard and screen detail panel:
<html>
<center>
 <table width="75%" border="2">
  <tr><td>
<a href="https://wepsim.github.io/wepsim/ws_dist/?mode=ep&examples_set=RISCV&example=14&simulator=assembly:keyboard&asm=FAYlAIHUFMAcGUCSBZcAKAFgFy7AzgFwD0RA7nHgJYC2AdAOaVYYCuARrZQPZkU1EBKUMGC0A1gBMAhlinBwCgG7QAxli4AnAgtqlNE8AFoAjPIXmLOvRoMmzly7v3gNWAPp4AnnhHis0AA8sYC88N1hXDywtcAAbSnMA4wVTBzT4xIAGBUz7NPM2aABHBQCAJgA2cADs6AA7CVT8tgBWbVi2RLKAdnBMtHKKoXzLQpLqnurahqaRhS4WLFLJzKTM9byRqQkDCarB6tm5sdLsqYVWzYV6xu08DWhgkO9wyMo6rHaE0uSjkZBwLAWHgMG42J5-GgAOQAHUyUOGcwUeE6pz6aDwsERSLw7GRsHAmMOVzSbHo0GW+2ybAAzCSHBkfgooYYofTLAsloccmsNkiFIzuUY-vlqCxYpS9sSRrTtACgSCwRDoGgHtQBgAaYyZAQAagALAAObFzAEBcAAXnAEkoik12pNI0FSXA2vZFjVy16ByS7vMNsUkp9IvS325Rr9Cm2u3K3smvv5cTDLpDDhRXV6-UxjvyuNRRKJCf5bDqFKlNXAtPZADMaXLARp3u48NF3vQMVjI+Bo-jCQSi0iOhn0dmuycJt7stWyl3OV6+rzconxxXzrWa2U7g8nuZIqFtAoAcZaIZCd4VFJYrEuz2pVJsjUu87Jvqx8Uo3HeqFXs3ok-k5MqajO+3afmeYQRO4TZdvcjy+P4QTANWUhqJolCXgQfoAngUjKC4UgaoS2RSA04BcKWcRcBeEqKFIjZSGwsQUuR4DMBSLYoWI4DVhoUjUNAfrRgkBYEiYM44qQu5SOAhodjmlh4JJyLZPqcmCTswnZESr5YeAlDVug97gAAPOAZQCC4jwsBodSun6GQBC0Zl+mSZZGVg1JuNAsR4AJg5hkZyQuSBFYVmwXnVj4SIAvphnZAAfFa5mWVg1m2UZABU3Eoeo9GxGg94mNi4Xeb5dxKd22SGKpeA6upNqVY1dhIgAVpeTLIaheX2RVWDJNVGJ1UiYoSo17mmLpDwtpoFJsYSsgqFxPF8X5FwRYQAoVbxMlqYOFW1eANWdkiQl9mdxgzpNVk2X6LUaPhIh5NQUjvNoulGVanW5eh+UtPJFiMkZLS3e1LpfWhl4iNFDZNm4TZoH1-3mIDvRAdc1HXrpgRMPZCRSKjS5zKol6Y0AA">https://wepsim.github.io/wepsim/ws_dist/?mode=ep&examples_set=RISCV&example=14&simulator=assembly:keyboard&asm=FAYlAIHUFMAcGUCSBZcAKAFgFy7AzgFwD0RA7nHgJYC2AdAOaVYYCuARrZQPZkU1EBKUMGC0A1gBMAhlinBwCgG7QAxli4AnAgtqlNE8AFoAjPIXmLOvRoMmzly7v3gNWAPp4AnnhHis0AA8sYC88N1hXDywtcAAbSnMA4wVTBzT4xIAGBUz7NPM2aABHBQCAJgA2cADs6AA7CVT8tgBWbVi2RLKAdnBMtHKKoXzLQpLqnurahqaRhS4WLFLJzKTM9byRqQkDCarB6tm5sdLsqYVWzYV6xu08DWhgkO9wyMo6rHaE0uSjkZBwLAWHgMG42J5-GgAOQAHUyUOGcwUeE6pz6aDwsERSLw7GRsHAmMOVzSbHo0GW+2ybAAzCSHBkfgooYYofTLAsloccmsNkiFIzuUY-vlqCxYpS9sSRrTtACgSCwRDoGgHtQBgAaYyZAQAagALAAObFzAEBcAAXnAEkoik12pNI0FSXA2vZFjVy16ByS7vMNsUkp9IvS325Rr9Cm2u3K3smvv5cTDLpDDhRXV6-UxjvyuNRRKJCf5bDqFKlNXAtPZADMaXLARp3u48NF3vQMVjI+Bo-jCQSi0iOhn0dmuycJt7stWyl3OV6+rzconxxXzrWa2U7g8nuZIqFtAoAcZaIZCd4VFJYrEuz2pVJsjUu87Jvqx8Uo3HeqFXs3ok-k5MqajO+3afmeYQRO4TZdvcjy+P4QTANWUhqJolCXgQfoAngUjKC4UgaoS2RSA04BcKWcRcBeEqKFIjZSGwsQUuR4DMBSLYoWI4DVhoUjUNAfrRgkBYEiYM44qQu5SOAhodjmlh4JJyLZPqcmCTswnZESr5YeAlDVug97gAAPOAZQCC4jwsBodSun6GQBC0Zl+mSZZGVg1JuNAsR4AJg5hkZyQuSBFYVmwXnVj4SIAvphnZAAfFa5mWVg1m2UZABU3Eoeo9GxGg94mNi4Xeb5dxKd22SGKpeA6upNqVY1dhIgAVpeTLIaheX2RVWDJNVGJ1UiYoSo17mmLpDwtpoFJsYSsgqFxPF8X5FwRYQAoVbxMlqYOFW1eANWdkiQl9mdxgzpNVk2X6LUaPhIh5NQUjvNoulGVanW5eh+UtPJFiMkZLS3e1LpfWhl4iNFDZNm4TZoH1-3mIDvRAdc1HXrpgRMPZCRSKjS5zKol6Y0AA</a>
  </td></tr>
 </table>
 </center>
</html>

For example, the following link loads the RISC-V assembly code for the factorial and shows the Elemental Processor and the register detail panel:
<html>
<center>
 <table width="75%" border="2">
  <tr><td>
<a href="https://wepsim.github.io/wepsim/ws_dist/?mode=ep&examples_set=RISCV&example=14&simulator=microcode:registers&asm=FAYlAIHUFMAcGUCSBZcAKAFgFy7AzgFwD0RA7nHgJYC2AdAOaVYYCuARrZQPZkU1EBKUMGC0A1gBMAhlinBwCgG7QAxli4AnAgtqlNE8AFoAjPIXmLOvRoMmzly7v3gNWAPp4AnnhHis0AA8sYC88N1hXDywtcAAbSnMA4wVTBzT4xIAGBUz7NPM2aABHBQCAJgA2cADs6AA7CVT8tgBWbVi2RLKAdnBMtHKKoXzLQpLqnurahqaRhS4WLFLJzKTM9byRqQkDCarB6tm5sdLsqYVWzYV6xu08DWhgkO9wyMo6rHaE0uSjkZBwLAWHgMG42J5-GgAOQAHUyUOGcwUeE6pz6aDwsERSLw7GRsHAmMOVzSbHo0GW+2ybAAzCSHBkfgooYYofTLAsloccmsNkiFIzuUY-vlqCxYpS9sSRrTtACgSCwRDoGgHtQBgAaYyZAQAagALAAObFzAEBcAAXnAEkoik12pNI0FSXA2vZFjVy16ByS7vMNsUkp9IvS325Rr9Cm2u3K3smvv5cTDLpDDhRXV6-UxjvyuNRRKJCf5bDqFKlNXAtPZADMaXLARp3u48NF3vQMVjI+Bo-jCQSi0iOhn0dmuycJt7stWyl3OV6+rzconxxXzrWa2U7g8nuZIqFtAoAcZaIZCd4VFJYrEuz2pVJsjUu87Jvqx8Uo3HeqFXs3ok-k5MqajO+3afmeYQRO4TZdvcjy+P4QTANWUhqJolCXgQfoAngUjKC4UgaoS2RSA04BcKWcRcBeEqKFIjZSGwsQUuR4DMBSLYoWI4DVhoUjUNAfrRgkBYEiYM44qQu5SOAhodjmlh4JJyLZPqcmCTswnZESr5YeAlDVug97gAAPOAZQCC4jwsBodSun6GQBC0Zl+mSZZGVg1JuNAsR4AJg5hkZyQuSBFYVmwXnVj4SIAvphnZAAfFa5mWVg1m2UZABU3Eoeo9GxGg94mNi4Xeb5dxKd22SGKpeA6upNqVY1dhIgAVpeTLIaheX2RVWDJNVGJ1UiYoSo17mmLpDwtpoFJsYSsgqFxPF8X5FwRYQAoVbxMlqYOFW1eANWdkiQl9mdxgzpNVk2X6LUaPhIh5NQUjvNoulGVanW5eh+UtPJFiMkZLS3e1LpfWhl4iNFDZNm4TZoH1-3mIDvRAdc1HXrpgRMPZCRSKjS5zKol6Y0AA">https://wepsim.github.io/wepsim/ws_dist/?mode=ep&examples_set=RISCV&example=14&simulator=microcode:registers&asm=FAYlAIHUFMAcGUCSBZcAKAFgFy7AzgFwD0RA7nHgJYC2AdAOaVYYCuARrZQPZkU1EBKUMGC0A1gBMAhlinBwCgG7QAxli4AnAgtqlNE8AFoAjPIXmLOvRoMmzly7v3gNWAPp4AnnhHis0AA8sYC88N1hXDywtcAAbSnMA4wVTBzT4xIAGBUz7NPM2aABHBQCAJgA2cADs6AA7CVT8tgBWbVi2RLKAdnBMtHKKoXzLQpLqnurahqaRhS4WLFLJzKTM9byRqQkDCarB6tm5sdLsqYVWzYV6xu08DWhgkO9wyMo6rHaE0uSjkZBwLAWHgMG42J5-GgAOQAHUyUOGcwUeE6pz6aDwsERSLw7GRsHAmMOVzSbHo0GW+2ybAAzCSHBkfgooYYofTLAsloccmsNkiFIzuUY-vlqCxYpS9sSRrTtACgSCwRDoGgHtQBgAaYyZAQAagALAAObFzAEBcAAXnAEkoik12pNI0FSXA2vZFjVy16ByS7vMNsUkp9IvS325Rr9Cm2u3K3smvv5cTDLpDDhRXV6-UxjvyuNRRKJCf5bDqFKlNXAtPZADMaXLARp3u48NF3vQMVjI+Bo-jCQSi0iOhn0dmuycJt7stWyl3OV6+rzconxxXzrWa2U7g8nuZIqFtAoAcZaIZCd4VFJYrEuz2pVJsjUu87Jvqx8Uo3HeqFXs3ok-k5MqajO+3afmeYQRO4TZdvcjy+P4QTANWUhqJolCXgQfoAngUjKC4UgaoS2RSA04BcKWcRcBeEqKFIjZSGwsQUuR4DMBSLYoWI4DVhoUjUNAfrRgkBYEiYM44qQu5SOAhodjmlh4JJyLZPqcmCTswnZESr5YeAlDVug97gAAPOAZQCC4jwsBodSun6GQBC0Zl+mSZZGVg1JuNAsR4AJg5hkZyQuSBFYVmwXnVj4SIAvphnZAAfFa5mWVg1m2UZABU3Eoeo9GxGg94mNi4Xeb5dxKd22SGKpeA6upNqVY1dhIgAVpeTLIaheX2RVWDJNVGJ1UiYoSo17mmLpDwtpoFJsYSsgqFxPF8X5FwRYQAoVbxMlqYOFW1eANWdkiQl9mdxgzpNVk2X6LUaPhIh5NQUjvNoulGVanW5eh+UtPJFiMkZLS3e1LpfWhl4iNFDZNm4TZoH1-3mIDvRAdc1HXrpgRMPZCRSKjS5zKol6Y0AA</a>
  </td></tr>
 </table>
 </center>
</html>


<a name="wepsim-gcolab"/>

### WepSIM from Google Colab

+ The following fragment is an example of how to integrate the WepSIM command-line within Google Colab cell:
  ```python
  !echo "(1/4) Installing pre-requisites..."
  !npm install  terser jq jshint yargs clear inquirer >& /dev/null
  !echo "(2/4) Downloading WepSIM..."
  !wget https://github.com/wepsim/wepsim/releases/download/v2.3.8/wepsim-2.3.8.zip >& /dev/null
  !unzip -o wepsim-2.3.8.zip  >& /dev/null
  !rm -fr   wepsim-2.3.8.zip
  !echo "(3/4) Executing WepSIM..."
  !./wepsim-2.3.8/wepsim.sh -a stepbystep -m ep -f ./wepsim-2.3.8/repo/microcode/mips/ep_base.mc -s ./wepsim-2.3.8/repo/assembly/mips/s1e1.asm > ./result.csv
  !rm -fr   wepsim-2.3.8
  !echo "(4/4) Showing execution trace as table..."

  import pandas as pd
  import io

  df1 = pd.read_csv('./result.csv')
  df1.columns = df1.columns.str.strip()
  for item in df1.columns[:]:
      df1[item].replace("\t","", inplace=True, regex=True)

  df1
  ```
+ The following fragment is an example of how to use WepSIM from Google Colab cell (web version):
  ```python
  from pathlib import Path
  import pandas as pd
  import io
  import lzstring
  from IPython.display import IFrame
  from google.colab import data_table

  def get_lz(filename):
    try:
      with open(filename,'r',encoding='utf-8') as f:
          cell_str = f.readlines()
          cell_str = ''.join(cell_str)
      x = lzstring.LZString()
      cell_lz = x.compressToBase64(cell_str)
    except:
      cell_lz = ''
    return cell_lz

  def get_ws_url(asm, cpu):
    url = 'https://wepsim.github.io/wepsim/ws_dist/?'
    url = url + 'mode=ep&'
    url = url + 'notify=false&'
    url = url + 'simulator=assembly:simulator&'
    url = url + 'examples_set=' + cpu + '&'
    url = url + 'example=11&'
    url = url + 'asm=' + asm
    return url

  def show_asm_in_ws(filename, cpu):
    try:
      lzasm = get_lz(filename)
      url   = get_ws_url(lzasm, cpu)
      display(IFrame(src=url, width="100%", height=700))
      status = 1
    except:
      status = 0
    return status

  !echo "(1/2) Getting s1e1.asm example..."
  !wget [ ! -f s1e1.asm ] && https://raw.githubusercontent.com/wepsim/wepsim/refs/heads/master/repo/assembly/rv32/s1e1.asm
  !echo "(2/2) Done!"
  show_asm_in_ws('s1e1.asm','RISCV')
  ```

