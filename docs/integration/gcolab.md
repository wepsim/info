

# Integrating WepSIM

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

