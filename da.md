一周混过去了好罪过



* 小程序好像也还没开始写项目

* 青训的笔试好像可能寄了


  ```js
  B.indexOf(A)//字符串匹配逆天编程题
  ```

* 好像尝试写了点东西(写了一半的Promise)

  ```js
  class Commitment {
      static PENDING = '待定'; static FULFILLED = '成功'; static REJECTED = '拒绝';
      constructor(func) {
          this.status = Commitment.PENDING;
          this.result = null;
          try { func(this.resolve, this.reject) } catch { this.reject(error) }
          func(this.resolve, this.reject)
      }
      resolve = (result) => {
          if (this.status === Commitment.PENDING) {
              this.status = Commitment.FULFILLED
              this.result = result
          }
      }
      reject = (result) => {
          if (this.status === Commitment.PENDING) {
              this.status = Commitment.REJECTED
              this.result = result
          }
      }
      then(onResolve, onRejected) {
          onResolve=typeof onResolve==='function' ? onResolve:{}
         onRejected=typeof onRejected==='function' ?onRejected:{}
          if (this.status === Commitment.FULFILLED)
                  onResolve(this.result)
          if (this.status === Commitment.REJECTED)
              onRejected(this.result)
      }
  }
  let p = new Commitment((resolve, reject) => {
      resolve('555')
  }).then(res => { console.log(res)})
  ```

  
