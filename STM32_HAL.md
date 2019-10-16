# HAL_StatusTypeDef HAL_UART_Receive_IT(UART_HandleTypeDef *huart, uint8_t *pData, uint16_t Size)
  **作用：串口huart接收Size个字符并存储在pData中后产生中断并调用HAL_UART_RxCpltCallback回调函数** 
## 注意：
 * 若串口一次接收到小于Size个字符则等待接收到Size个字符后才会产生中断。
 * 若串口一次接收到Size+1个字符，则多余一个字符留在下一次接收，若下次接收到Size - 1个字符，则接收正常。
 * 若串口一次接收到大于Size+1，则会产生错误，并调用HAL_UART_ErrorCallback回调函数。建议在HAL_UART_ErrorCallback回调函数调用HAL_UART_Receive_IT函数以便串口继续工作。
 * 经测试发现HAL_UART_Receive_IT一次只能接收不大于20个字符，否则产生HardFault错误。