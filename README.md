from PyQt5.QtCore import Qt
from PyQt5.QtWidgets import *
    
radio = QApplication([])

radio_num = QWidget()
radio_num.setWindowTitle("Моё первое приложение")
radio_num.resize(500,200)

check = QPushButton("Проверить")

button_1 = QRadioButton("1")
button_2 = QRadioButton("2")
button_3 = QRadioButton("3")

button_group = QButtonGroup()
button_group.addButton(button_1, id = 1)
button_group.addButton(button_2, id = 2)
button_group.addButton(button_3, id = 3)

button_2.setChecked(True)
    
res = QLabel(" ")

def f():
    res.setText("Выбрана кнопка под номером " + str(button_group.checkedId()))

check.clicked.connect(f)

v_line = QVBoxLayout()
l_line_1 = QHBoxLayout()
l_line_2 = QHBoxLayout()
l_line_3 = QHBoxLayout()
l_line_4 = QHBoxLayout()
l_line_5 = QHBoxLayout()

l_line_4.addWidget(check, alignment = Qt.AlignCenter)
l_line_1.addWidget(button_1, alignment = Qt.AlignLeft)
l_line_2.addWidget(button_2, alignment = Qt.AlignLeft)
l_line_3.addWidget(button_3, alignment = Qt.AlignLeft)
l_line_5.addWidget(res, alignment = Qt.AlignCenter)

v_line.addLayout(l_line_1)
v_line.addLayout(l_line_2)
v_line.addLayout(l_line_3)
v_line.addLayout(l_line_4)
v_line.addLayout(l_line_5)



radio_num.setLayout(v_line)
radio_num.show()
radio.exec_()
